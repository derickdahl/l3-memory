# Slack Integration Config

**Setup Date:** 2026-01-27
**Status:** Active

## Bot Details
- **Workspace:** Sonance (sonance-slack.slack.com)
- **Bot User:** l3
- **Bot ID:** B0AB9A8QY9K
- **User ID:** U0AC728PQD6

## Token
Stored in: Clawdbot config (`channels.slack.botToken`)

## Capabilities
Via the `slack` skill:
- Send messages
- Read messages
- React to messages
- Pin/unpin messages
- Get member info
- List custom emoji

## Usage Examples
```json
// Send a message
{"action": "sendMessage", "to": "channel:C123", "content": "Hello!"}

// React to a message
{"action": "react", "channelId": "C123", "messageId": "1712023032.1234", "emoji": "✅"}

// Read recent messages
{"action": "readMessages", "channelId": "C123", "limit": 20}
```

## Notes
- Bot needs to be invited to channels to read/write
- DM policy: allowlist (needs to be configured for specific users)
