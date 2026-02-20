# Simli Integration Notes
**Date:** 2026-02-20

## API Key
Stored: ~/.clawdbot/credentials/simli-api-key

## Custom Face
- Uploaded Elle headshot 2/20 — in queue, up to 24hrs
- Face ID will appear at https://app.simli.com under "Your Avatars"

## Preset Faces (for testing NOW)
- Tina: cace3ef7-a4c4-425d-a8cf-a5358eb0c427
- Laila: b9e5fba3-071a-4e35-896e-211c4d6eaa7b

## Recommended Architecture: LiveKit
Simli recommends LiveKit over raw WebRTC.
- LiveKit handles room management, WebRTC complexity
- Native plugin: `livekit-plugins-simli`
- Python-based agent: livekit-agents SDK

### LiveKit Setup
1. Account at livekit.io — need "Video conference" Sandbox project
2. Env vars: LIVEKIT_URL, LIVEKIT_API_KEY, LIVEKIT_API_SECRET
3. Python deps: livekit-agents[openai], livekit-plugins-simli, python-dotenv

### Key Code Pattern
```python
from livekit.agents import Agent, AgentSession, JobContext, WorkerOptions, cli
from livekit.plugins import openai, simli

async def entrypoint(ctx: JobContext):
    session = AgentSession(llm=openai.realtime.RealtimeModel(voice="alloy"))
    simli_avatar = simli.AvatarSession(
        simli_config=simli.SimliConfig(api_key=KEY, face_id=FACE_ID)
    )
    await simli_avatar.start(session, room=ctx.room)
    await session.start(agent=Agent(instructions="..."), room=ctx.room)
```

## Other API Endpoints
- Create avatar: POST to app.simli.com
- Delete face: permanent, breaks connected agents
- Generate static video: from audio sample
- Compose session token: for WebRTC sessions
- Active session count: monitoring

## Docs
- Overview: https://docs.simli.com/overview
- LiveKit guide: https://docs.simli.com/api-reference/livekit
- Preset faces: https://docs.simli.com/api-reference/preset-faces
- Full index: https://docs.simli.com/llms.txt
