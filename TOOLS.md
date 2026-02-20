# TOOLS.md - Essential Integration Quick Reference

*Core integrations only - full docs moved to `memory/tools-detailed.md` to reduce context window*

## 🔑 Active Integrations

### Microsoft Graph (Outlook/Calendar)
**Helper:** `~/.clawdbot/scripts/msgraph.sh token|call`
**Permissions:** Mail, Calendar, Chat, Files

### Asana (Tasks)
**Token:** `~/.clawdbot/credentials/asana-token`
**Workspace:** 1201171894258423
**Projects:** Derick Private (1202127678978097)

### VAPI (Voice AI)  
**Dashboard:** https://dashboard.vapi.ai
**Assistants:** L3 Voice, Sonance Tech Support

### GoDaddy (DNS)
**Auth:** `~/.clawdbot/credentials/godaddy-key` + `godaddy-secret`

### Salsify (Product Data)
**Auth:** `~/.clawdbot/credentials/salsify-api-key`
**Data:** 4,540+ products, images, pricing

## 🎤 Voice (ElevenLabs)
**Voice:** Lily (pFZP5JQG7iQjIQuC4Bku) @ 1.35x speed
**Command:** `sag -v pFZP5JQG7iQjIQuC4Bku --speed 1.35`

### Google Vertex AI (Veo Video Generation)
**Service Account:** `~/.clawdbot/credentials/google-vertex-ai.json`
**Project:** `gen-lang-client-0081847213`
**Email:** `elle-vertex-ai@gen-lang-client-0081847213.iam.gserviceaccount.com`
**Models:** Veo 2.0 (`veo-2.0-generate-001`), Veo 3.1 when available
**Endpoint:** `https://us-central1-aiplatform.googleapis.com/v1/projects/{project}/locations/us-central1/publishers/google/models/{model}:predictLongRunning`
**Capabilities:** Text-to-video, image-to-video (start frame), 4-8 sec clips, 1080p
**Auth:** Service account JWT → Bearer token via `google.oauth2.service_account`

## 🚀 SaaS Stack
**Pipeline:** GitHub → Supabase → Vercel → Stripe
**Domains:** 22 available via GoDaddy API

## 🍽️ Auto-Orders (11am-1pm only)
- **Poke:** Full Wowpoki order, Amex 6003
- **Thai:** Tom Ka Soup order

**Details:** See `memory/tools-detailed.md` for full documentation

*Context-optimized version - Last updated: 2026-02-07*

