# HEARTBEAT.md

## Periodic Tasks

### Aron Mckay Teams DM (check every heartbeat until resolved)
Monitor for new messages from Aron in the Teams DM about M365/Asana setup:
```
ARON_CHAT="19:3acfd933-4bae-4f2b-99e3-0d3049b3946f_482506e7-da50-4820-8426-1ca92a6fc4a3@unq.gbl.spaces"
~/.clawdbot/scripts/msgraph.sh call "/chats/$ARON_CHAT/messages?\$top=5&\$orderby=createdDateTime desc" 2>/dev/null | jq '[.value[] | {id, from: .from.user.displayName, time: .createdDateTime, content: .body.content[:200]}]'
```
- If Aron replied with questions → answer them directly in the Teams DM
- If no new messages from Aron → skip, check next heartbeat
- **Remove this section** once Aron confirms he's all set

### Josh Blanken Teams DM (check every heartbeat until resolved)
Monitor for new messages from Josh in the Teams DM about Asana/Jarvis setup:
```
CHAT_ID="19:361f6c1f-a191-4ec2-b5fe-32806c94b1ad_3acfd933-4bae-4f2b-99e3-0d3049b3946f@unq.gbl.spaces"
~/.clawdbot/scripts/msgraph.sh call "/chats/$CHAT_ID/messages?\$top=5&\$orderby=createdDateTime desc" 2>/dev/null | jq '[.value[] | {id, from: .from.user.displayName, time: .createdDateTime, content: .body.content[:200]}]'
```
- If Josh replied with questions → answer them directly in the Teams DM
- If no new messages from Josh → skip, check next heartbeat
- **Remove this section** once Josh confirms he's all set

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

