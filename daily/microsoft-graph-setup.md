# Microsoft Graph Integration - COMPLETE

**Setup Date:** 2026-01-27
**Status:** ✅ Active and working

## Azure AD App Registration

- **App Name:** L3 Assistant
- **Application (client) ID:** ecd755cc-2393-4d89-83b8-290436a138e5
- **Directory (tenant) ID:** ae4bbd35-942c-4c35-b794-274bc9cdd718
- **Secret ID:** 10a54691-b66e-4486-b5d4-4804e82ee8a3

## Permissions Granted

- Mail.Read - Read emails
- Mail.Send - Send emails
- Calendars.ReadWrite - Read/write calendar
- Chat.Read - Read Teams chats
- Files.Read.All - Read OneDrive/SharePoint files
- User.Read - Read user profile

## Credential Files

- `~/.clawdbot/credentials/microsoft-graph.json` - App credentials
- `~/.clawdbot/credentials/microsoft-tokens.json` - Access/refresh tokens

## Helper Script

`~/.clawdbot/scripts/msgraph.sh` - Token management and API calls

Usage:
```bash
# Get current access token
~/.clawdbot/scripts/msgraph.sh token

# Force token refresh
~/.clawdbot/scripts/msgraph.sh refresh

# Make Graph API call
~/.clawdbot/scripts/msgraph.sh call "/me/messages?\$top=5"
```

## Direct API Examples

```bash
TOKEN=$(~/.clawdbot/scripts/msgraph.sh token)

# Get profile
curl -H "Authorization: Bearer $TOKEN" "https://graph.microsoft.com/v1.0/me"

# Get emails
curl -H "Authorization: Bearer $TOKEN" "https://graph.microsoft.com/v1.0/me/messages?\$top=10"

# Get calendar
curl -H "Authorization: Bearer $TOKEN" "https://graph.microsoft.com/v1.0/me/calendarview?startDateTime=2026-01-28T00:00:00&endDateTime=2026-01-28T23:59:59"

# Send email
curl -X POST -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" \
  -d '{"message":{"subject":"Test","body":{"contentType":"Text","content":"Hello"},"toRecipients":[{"emailAddress":{"address":"someone@example.com"}}]}}' \
  "https://graph.microsoft.com/v1.0/me/sendMail"
```

## Token Refresh

- Access tokens expire in ~1 hour
- Refresh tokens last 90 days (with activity)
- Helper script auto-refreshes on 401 errors

## Next Steps

- [ ] Add more permissions as needed (Teams posting, SharePoint write, etc.)
- [ ] Build Clawdbot skill for common operations
- [ ] Set up calendar/email monitoring in heartbeat
