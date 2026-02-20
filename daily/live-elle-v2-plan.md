# Live Elle v2 - Real-Time Avatar Plan

## Decision: Simli API (Option A) ✅

**Why Simli wins:**
- Real-time: <300ms latency (vs minutes for SadTalker/LivePortrait)
- JavaScript SDK available (`simli-client`)
- WebRTC streaming (just like HeyGen)
- Cloud-based (works from anywhere)
- PCM16 audio format support
- Working examples and docs available

## Architecture Overview

**Current:** HeyGen Streaming Avatar SDK → Katya avatar
**New:** Simli API → Custom Elle face

**Keep unchanged:**
- Claude brain API (`/api/claude/chat`)
- ElevenLabs voice (already generates audio)
- Speech recognition (Web Speech API)
- Next.js 14 app structure

**Replace:**
- `@heygen/streaming-avatar` → `simli-client`
- HeyGen token/session → Simli API key
- Video stream handling (similar WebRTC approach)

## Implementation Steps

### Phase 1: Setup Simli Integration
1. Get Simli API key (sign up at simli.com)
2. Choose/create Elle avatar face ID
3. Install `simli-client` and `standardized-audio-context`
4. Replace HeyGen initialization with Simli

### Phase 2: Audio Pipeline
1. Modify ElevenLabs response to get raw audio
2. Convert audio to PCM16 format @ 16kHz
3. Stream audio chunks to Simli (100ms chunks)
4. Handle lip-sync timing

### Phase 3: Video Integration
1. Update AvatarVideo component for Simli WebRTC
2. Replace HeyGen event handlers with Simli events
3. Maintain same UI/UX (connection status, speaking indicator)

### Phase 4: Deploy & Test
1. Update environment variables
2. Deploy to Vercel
3. Test real-time performance
4. Document any issues/optimizations

## Key Technical Changes

```javascript
// OLD: HeyGen
import StreamingAvatar from '@heygen/streaming-avatar'
const avatar = new StreamingAvatar({ token })
await avatar.createStartAvatar({ avatarName: 'Katya_CasualLook_public' })

// NEW: Simli
import { SimliClient } from 'simli-client'
const simliClient = new SimliClient()
const config = { apiKey, faceID: 'elle_face_id', videoRef, audioRef }
simliClient.Initialize(config)
await simliClient.start()
```

## Audio Processing Requirements
- Input: ElevenLabs MP3/AAC audio
- Output: PCM16 chunks @ 16kHz, 100ms intervals
- Use AudioContext for downsampling/chunking

## Risk Assessment
- **Low Risk:** Simli has proven WebRTC integration
- **Medium Risk:** Audio format conversion complexity
- **Low Risk:** Face ID creation (can use existing avatars initially)

## Fallback Plan
If Simli integration fails:
- **Option B:** Pre-rendered viseme approach with LivePortrait
- **Option C:** Canvas-based mouth animation

## Success Criteria
- ✅ Real-time lip-sync (<500ms total latency)
- ✅ Maintains existing conversation flow
- ✅ Deployed and accessible from anywhere
- ✅ Stable WebRTC connection
- ✅ Quality audio-visual sync

---
**Status:** Planning Complete - Ready for Implementation
**Next:** Get Simli API key and start Phase 1