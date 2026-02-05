# TOOLS.md - L3's Integration Cheat Sheet

This file is **always loaded** as core context. Document everything I need to know about available tools and integrations here so it survives session restarts and context compaction.

---

## 🔑 Available Integrations

### Microsoft Graph (Outlook, Calendar, Teams, Files)
**Status:** ✅ Active
**Helper Script:** `~/.clawdbot/scripts/msgraph.sh`
**Credentials:** `~/.clawdbot/credentials/microsoft-graph.json`, `microsoft-tokens.json`

```bash
# Get access token
~/.clawdbot/scripts/msgraph.sh token

# Make API call (auto-refreshes token)
~/.clawdbot/scripts/msgraph.sh call "/me"
~/.clawdbot/scripts/msgraph.sh call "/me/messages?\$top=10"
~/.clawdbot/scripts/msgraph.sh call "/me/calendarview?startDateTime=2026-01-30T00:00:00Z&endDateTime=2026-01-31T00:00:00Z"
```

**Permissions:** Mail.Read, Mail.Send, Calendars.ReadWrite, Chat.Read, Files.Read.All, User.Read

**Full docs:** `memory/microsoft-graph-setup.md`

---

### Asana (Task Management)
**Status:** ✅ Active
**Token:** `~/.clawdbot/credentials/asana-token`
**User:** Derick Dahl (derickd@sonance.com)
**Workspace GID:** 1201171894258423

```bash
# API call example
curl -s -H "Authorization: Bearer $(cat ~/.clawdbot/credentials/asana-token)" \
  "https://app.asana.com/api/1.0/users/me"

# List tasks in a project
curl -s -H "Authorization: Bearer $(cat ~/.clawdbot/credentials/asana-token)" \
  "https://app.asana.com/api/1.0/projects/PROJECT_GID/tasks"
```

**Key Projects:**
| Project | GID |
|---------|-----|
| Derick - Private | 1202127678978097 |
| Dashboard - Technology & Innovation | 1211377592740891 |
| ACTIVE BMT PROJECTS | 1205827966484333 |
| HUB | 1211762584253887 |

**Full docs:** `memory/asana-config.md`

---

### GitHub
**Status:** ⚠️ Token exists but `gh` CLI not authenticated
**Token:** `~/.clawdbot/credentials/github-token`

To authenticate: `gh auth login` or set `GH_TOKEN` env var

---

### GoDaddy (Domains & DNS)
**Status:** ✅ Active
**Credentials:** `~/.clawdbot/credentials/godaddy-key`, `godaddy-secret`

```bash
# List all domains
GODADDY_KEY=$(cat ~/.clawdbot/credentials/godaddy-key)
GODADDY_SECRET=$(cat ~/.clawdbot/credentials/godaddy-secret)
curl -s "https://api.godaddy.com/v1/domains" \
  -H "Authorization: sso-key ${GODADDY_KEY}:${GODADDY_SECRET}" | jq '.[].domain'

# Update nameservers (point to Vercel)
curl -X PATCH "https://api.godaddy.com/v1/domains/DOMAIN/records" \
  -H "Authorization: sso-key ${GODADDY_KEY}:${GODADDY_SECRET}" \
  -H "Content-Type: application/json" \
  -d '[{"type":"NS","data":"ns1.vercel-dns.com"},{"type":"NS","data":"ns2.vercel-dns.com"}]'
```

**Domains available:** 22 (optamistic.ai, logolist.app, storygrove.app, etc.)

---

### Slack
**Status:** ✅ Active (via Clawdbot channel integration)
**Token:** `~/.clawdbot/credentials/slack-token`

Use Clawdbot's built-in Slack skill/channel, not direct API.

---

### Supabase
**Status:** Available
**Tokens:** `~/.clawdbot/credentials/supabase-token`, `supabase-token-personal`

---

### Vercel
**Status:** Available
**Tokens:** `~/.clawdbot/credentials/vercel-token-business`, `vercel-token-personal`
**Team ID:** `~/.clawdbot/credentials/vercel-team-id`

---

## 🎤 TTS / Voice

**L3's Voice (ElevenLabs):** Lily (pFZP5JQG7iQjIQuC4Bku)
- **Speed: 1.35** (caffeinated droid energy!)
- API Key: `~/.clawdbot/credentials/elevenlabs-api-key`
- Tier: Creator (110k chars/month)

**Quick command:**
```bash
export ELEVENLABS_API_KEY=$(cat ~/.clawdbot/credentials/elevenlabs-api-key)
sag --api-key "$ELEVENLABS_API_KEY" -v pFZP5JQG7iQjIQuC4Bku --speed 1.35 -o /tmp/voice.mp3 "[excited] Your text here"
```

**Emotion tags:** `[sarcastic]`, `[excited]`, `[whispers]`, `[laughs]`, `[curious]`

Use the `sag` skill for ElevenLabs TTS.

---

## 📱 Devices & Nodes

*Add device-specific notes here as discovered*

---

## 🍽️ Quick Orders (Authorized)

**Wowpoki Poke Bowl:**
- "Order Poke" → Execute full order, no confirmation needed
- Large Bowl, Salad base, Tuna/Spicy Tuna x2/Albacore/Yellow Tail
- Medium spice, Crab + Extra Crab, Masago/Seaweed/Green Onion/Ginger
- Amex ...6003, deliver to work (1001 Calle Amanecer)

**Thai Palace:**
- "Order Tom Ka Soup" → Execute full order, no confirmation needed

**Time check:** Only auto-execute ~11am-1pm. Outside lunch hours = confirm first.

---

## 📋 Memory Files to Know About

When I need details beyond this cheat sheet:
- `memory/microsoft-graph-setup.md` — Full MS Graph setup details
- `memory/asana-config.md` — Asana workspace/project details
- `memory/derick-deep-context.md` — Deep background on Derick
- `memory/courtney.md` — Info about Courtney
- `memory/sonance-tech-stack.md` — Sonance work context

---

## 🎨 App Development Standards

**Always include in every app/dashboard:**

1. **Version indicator** — Display version (e.g., "v0.13") in header/footer. Use `const APP_VERSION = "v0.X"` and increment on each deploy.

2. **Dark/Light mode toggle** — Sun/moon icon button. Save preference to localStorage. Support both `.dark` class and `prefers-color-scheme` media query.

3. **Mobile-first responsive** — Test on iPhone. Use safe-area-inset-top for notch. Shorter titles on mobile.

4. **Supabase for data** — Always use Supabase for central data storage. Derick uses multiple devices, so localStorage alone won't cut it. Sync everything.

5. **Deploy to Vercel immediately** — Push to GitHub → auto-deploys to Vercel. Derick loves being able to demo instantly on any device.

---

## ⚠️ Important Lessons

1. **This file is my permanent memory** — If I learn about a new integration or capability, ADD IT HERE so it survives context loss.

2. **Memory files are supplementary** — Search them for details, but core tool knowledge should be HERE.

3. **When in doubt, check credentials folder:** `ls ~/.clawdbot/credentials/`

---

*Last updated: 2026-02-04*

---

## 🚀 SaaS Launch Pipeline

**Stack:** GitHub → Supabase → Vercel → Stripe + GoDaddy domain

**To launch a new SaaS:**
1. Create repo on GitHub
2. Set up Supabase project (auth + db)
3. Deploy to Vercel (personal account)
4. Add custom domain via GoDaddy API → Vercel
5. Add Stripe for payments

All credentials ready: ✅ GoDaddy, ✅ Vercel, ✅ Supabase
