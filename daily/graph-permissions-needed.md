# Microsoft Graph API - Permissions Needed

**For:** Trevan (IT Admin approval)
**App:** L3 Assistant
**Last Updated:** 2026-01-29

---

## Currently Have ✅
| Permission | What it does |
|------------|--------------|
| User.Read | Read my own profile |
| Mail.Read | Read emails |
| Mail.Send | Send emails |
| Calendars.ReadWrite | Create/edit calendar events |
| Chat.Read | Read Teams chats |
| Files.Read.All | Read OneDrive/SharePoint files |

---

## Need to Add 🔜

| Permission | What it enables | Why I need it |
|------------|-----------------|---------------|
| **Mail.ReadWrite** | Mark emails read/unread, move to folders, delete | Inbox triage - mark spam as read, move to junk, organize |
| **User.Read.All** | Search company directory (GAL) | Look up coworker emails when scheduling meetings |
| **People.Read** | Access contacts & frequent collaborators | Find people without needing full directory access |

---

## Maybe Later 🤔

| Permission | What it enables | Use case |
|------------|-----------------|----------|
| Contacts.ReadWrite | Manage Outlook contacts | Add/update contact info |
| Tasks.ReadWrite | Manage To Do / Planner tasks | Sync with Asana or create tasks |
| Team.ReadBasic.All | Read Teams membership | Know who's in which team |
| Presence.Read.All | See availability status | Check if someone is free before scheduling |

---

## Notes for Trevan
- All permissions are **delegated** (act on behalf of Derick, not app-only)
- No admin-consent-only permissions in the immediate list
- User.Read.All may require admin consent depending on tenant config
