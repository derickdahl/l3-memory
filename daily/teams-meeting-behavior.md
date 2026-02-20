# Elle Teams Meeting Behavior Spec
**Created:** 2026-02-20

## During Meeting

### Input
- Live Teams transcription stream (already enabled for all Sonance meetings)
- Speaker identification handled by Teams (per-computer + in-room voice/face detection)

### Behavior Modes
1. **Silent Observer (default)** — listening, tracking context, taking notes
2. **Active Response** — triggered by wake word or direct question

### Wake Words / Triggers
- "Elle" or "L3" spoken in meeting
- Direct questions addressed to me
- @mentions in Teams meeting chat

### Response Pipeline
Brain (Claude) → ElevenLabs (Lily voice) → Simli (lip sync) → Virtual mic/cam → Teams

## Post-Meeting

### 1. Meeting Summary
- Send as Teams group DM to all meeting attendees
- Include: key decisions, discussion points, outcomes
- Use Microsoft Graph API to send (already have access)

### 2. Action Items → Asana
- Identify action items from transcript
- Create Asana tasks in Sonance workspace (1201171894258423)
- Assign to correct person (need Teams display name → Asana user ID mapping)
- Tasks land in assignee's "My Tasks" inbox — they move to appropriate project
- Tag with meeting name/date for traceability

### Needs
- [ ] ~~Teams display name → Asana user ID mapping table~~ SOLVED: Dynamic lookup via email (Teams display name → Graph API email → Asana user by email). Will be even cleaner after Asana Enterprise + AD sync.
- [ ] Transcript stream access method (Graph API vs UI scraping)
- [ ] Face ID from Simli (headshot uploaded 2/20, queue says up to 24hrs — ask Derick when ready)
- [ ] Test meeting to validate full pipeline
