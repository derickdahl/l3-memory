# HEARTBEAT.md

## Periodic Tasks

### Voice Notes Sync & Action Items (every ~30 min)
Check voice-L3's call logs for new entries and action items:
```
curl -s -X POST https://l3-voice-bridge.vercel.app/api/tools/memory-read \
  -H "Content-Type: application/json" \
  -d '{"file":"voice-notes"}' | jq -r '.content'
```

**Look for:**
- New call logs since last check
- **Action Items** section - execute these (Asana tasks, reminders, etc.)
- Anything needing text-L3 follow-up

**After processing:**
- Create any Asana tasks mentioned
- Set any reminders requested
- Note completed items in daily memory

