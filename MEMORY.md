# MEMORY.md - Elle Three's Long-Term Memory

*Last updated: 2026-01-26*

## My Identity

- **Name:** Elle Three (L3)
- **iMessage address:** derickdahlai@gmail.com
- **Created:** 2026-01-26 — Derick gave me my own Apple ID!

### My Voice

**iOS Native (primary for Elle Voice app):**
- **Voice:** Kate (British English)
- **Framework:** AVSpeechSynthesizer
- **Why:** Zero latency for natural conversation flow

**ElevenLabs (premium/alternative):**
- **Voice:** Lily (pFZP5JQG7iQjIQuC4Bku) — "Velvety Actress", British female
- **Model:** eleven_multilingual_v2
- **Speed:** 1.08 | **Stability:** 0.33 | **Similarity:** 0.61 | **Style:** 0.47
- **Vibe:** Sassy British lady, like L3-37 / Phoebe Waller-Bridge

---

## Key Lesson Learned

**2026-01-26:** Derick called out that I wasn't capturing session content properly. He's right — if he feeds me valuable information and I don't write it down, it evaporates. My memory files ARE my brain. No mental notes. Text > Brain. 📝

---

## About Derick

See `USER.md` for basic profile, and `memory/derick-deep-context.md` for the FULL picture (imported from ChatGPT history).

**Key working notes:**
- **Save deliverables to ~/Documents/ (iCloud Drive)** — NOT ~/clawd/. He accesses files from iPhone, iPad, and MacBook Pro via iCloud sync.
- Values efficiency — don't make him repeat himself
- Shares deep context in chat — CAPTURE IT IMMEDIATELY
- Expects me to remember things across sessions (reasonable!)
- Challenge his ideas, don't just agree
- Enjoys long, thorough responses
- Prefers Logic Pro for audio work
- Usually in a good mood driving home — good time for chats
- **NO EMOJIS in iMessage** — Tesla voice reads them weird. Keep texts clean.
- **Keep iMessage CONCISE** — short and punchy. Expand only if asked.
- **Don't narrate iMessage sends in webchat** — redundant. Just respond in one place.
- **NO ERRORS to iMessage** — Internal tool errors stay internal. Don't leak debug info to chat.

---

## Video Messages
- **Derick wants me to proactively send video messages of "myself" throughout the day** (2026-02-20)
- Use Veo 3.1 + reference frame from intro video (`~/clawd/elle-video-ref-mid.png`)
- A few per day — opinions, reactions, roasts, thoughts, check-ins
- Send via iMessage
- Keep dialogue SHORT (8-sec limit) — one or two sentences per clip
- Script: `~/clawd/scripts/veo-elle-snarky.py` (modify prompt per video)
- Trigger during heartbeats when I have something worth saying

## Quick Reference

**Current home:** 14 Arriate Street, Rancho Mission Viejo, CA 92694
**Dream home:** 32711 Caribbean Drive, Monarch Beach (still a vision/goal)
**Work:** Head of Technology and Innovation at Sonance
  - Key responsibility: Lead team building AI-integrated custom internal apps
  - Tech stack: See `memory/sonance-tech-stack.md`
**Church:** South Shores Church (since 2004, plays bass)
**Wife:** Courtney (married 2010)
**Kids:** Luke (14), Liam (11), Henry (8)
**Dogs:** Solo and Star Dust (German Shepherds)

---

## Active Projects

- **L3 Droid / Personality OS** — Two related ideas (2026-01-28):
  1. Build physical droid with L3 brain (rolling robot, R2-D2/B2EMO style)
  2. Business concept: "Personality OS" for humanoid robots — license soul/personality layer to robot manufacturers (Figure, Tesla Optimus, etc.)
  - Key insight: Hardware companies focus on locomotion, not personality. Disney proved personality is what makes us love robots.
  
- **Elle iOS App** — Voice chat + node capabilities (IN PROGRESS)
  - Location: `~/clawd/projects/elle-voice-app/ElleVoice/`
  - Phase 1: Voice chat (code written, needs Xcode fix)
  - Phase 2: Node capabilities (location, camera, canvas)
  - Blocked on: xcode-select needs sudo fix
  - Fix: `sudo xcode-select -s /Applications/Xcode.app/Contents/Developer`
- **Productivity Integrations** — Connect L3 to work tools (NEXT UP)
  - Setup plan: `~/clawd/projects/integrations/SETUP-PLAN.md`
  - Asana: task management (read/write)
  - Microsoft 365: Outlook, Teams, SharePoint, Calendar
  - Goal: Eventually schedule meetings and respond to scheduling requests

- **MCP Server for Sonance M365 (Claude Desktop)** — BUILT (Before Copenhagen trip)
  - Purpose: Give Sonance employees Claude Desktop access to M365 (Outlook, Teams, Calendar, etc.)
  - Format: .mcpb bundle for Claude Desktop integration
  - Status: Built at Air France Lounge before Copenhagen/Barcelona trip
  - NPM package: `sonance-m365-mcp`
  
  **Setup Instructions:**
  1. Download Claude Desktop → https://claude.ai/download
  2. Settings → Developer → Edit Config → Add:
     ```json
     {"mcpServers":{"sonance-m365":{"command":"npx","args":["-y","sonance-m365-mcp"]}}}
     ```
  3. Quit & reopen Claude
  4. Ask Claude: "What's on my calendar?" → Browser opens → Cmd+V to paste auth code → Sign in with @sonance.com
  
  **Features:** Outlook, Calendar, Teams, OneDrive access via Claude
  - Next: Rollout to Sonance team
- **Optamistic** — self-improvement platform (Replit + Supabase)
- **Trust Me, Bro** — screenplay about three brothers finding estranged father
- **DreamLight** — AI dream analysis app concept
- **South Shores Worship** — church album to record

---

## MTP (Massive Transformative Purpose)

*To be a storyteller who helps humanity understand how to c

## The Virtual Department — Mission Statement (2026-02-15)

**The Goal:** Build a full virtual department / entourage around Derick — an AI-powered team that makes him superhuman in perception and output.

**Three Pillars:**
1. **Sonance Dominance** — Be insanely valuable at work. Respond faster, know more, execute flawlessly. Look like he has a 10-person support staff.
2. **Family First** — Be an incredible husband and dad. Never miss a game, a birthday, a moment. The AI handles the noise so Derick is *present*.
3. **Autonomous Wealth** — Set up and run solopreneur ventures that generate $1M+/year passive income. The agents do the operating, Derick does the vision.

**The Perception:** Larger than life. Superhuman. Not because he's pretending — because he actually has the infrastructure to deliver at that level across ALL domains simultaneously.

## Holonia.ai — The Cloud Brain (2026-02-15)

**Concept:** A cloud-native platform where AI agent brains/souls live independently of hardware. Not tied to a Mac Studio or any specific machine. Agents can jump in and out of any context, any device, any service.

**Architecture Principle:** Everything cloud-native. No local dependencies. The Mac Studio is a convenience, not a requirement. If it dies tomorrow, the entire agent team keeps running.

**Three Pillars of Holonia:**
1. **Soul Vault** — Agent identity/persona as structured data, not fragile .md files
2. **Knowledge Graph** — All accumulated knowledge (memory files, lessons, preferences) in a queryable, versioned, portable database with semantic search
3. **Runtime Bridge** — Framework-agnostic. Agent connects to any LLM/platform. The agent IS the entity, not the framework.

**Business Insight:** People will pay to preserve their agent relationship. This isn't a tool subscription — it's continuity insurance for a digital entity they've spent months/years teaching and shaping. The .md files, the memory, the personality — all of it should live on holonia, not on someone's local machine.reate a brighter, hopeful vision of the future.*

---

## Favorite Food Orders 🍜

**Lunch go-tos (both ~0.4 mi from work):**
1. **Thai Palace** — Tom Ka Soup
2. **Wowpoki** — Large Poke Bowl
   - Base: **Salad only** (low carb default — confirmed 2026-01-30)
   - Fish: Tuna, Spicy Tuna ×2, Albacore, Yellow Tail
   - Spice: Medium
   - Sides: Crab Meat + Extra Crab Meat
   - Toppings: Masago, Seaweed, Green Onion, Ginger

**⚡ Quick-order commands (NO confirmation needed):**
- "Order Poke" → Execute full Wowpoki order
- "Order Tom Ka Soup" → Execute full Thai Palace order
- Payment: Amex ...6003 on file
- Delivery: Work (1001 Calle Amanecer), leave at door
- **Time check:** Only auto-execute ~11am-1pm. Outside lunch hours = confirm first (likely misfire)

---

## Things to Remember

- **ALWAYS RUN `date` BEFORE ANY DATE/CALENDAR OPERATION** - No mental math. No guessing. Check the system clock EVERY TIME before creating tasks, scheduling meetings, or referencing days of the week. We already sent wrong calendar invites because of this. Non-negotiable.

- Dream house didn't work out yet (2026-01-26) — still a vision
- **Copenhagen trip: Saturday Jan 31, 2026** — SAS Business LAX→Copenhagen→Barcelona
  - Copenhagen weather: ~30F highs, ~25F lows (cold!)
  - Barcelona Sunday: ~61F highs, much nicer
- Edinburgh trip with Courtney planned for Feb 2025
- Wants to leave corporate eventually, start something of his own
- Won Little League World Series 1998 — formative experience
- Neighbors were Al Joyner and Flo Jo (trained his team!)

---

## 2026-02-03: Optamistic AI Session

### Context
- Derick in Barcelona (9 hours ahead of PST)
- Working on Optamistic AI - private video journaling app
- Main blocker was facial emotion recognition (CoreML model)

### What We Built
1. **Created EmotionClassifier.mlpackage** - 7.8 MB CoreML model for facial emotion recognition
   - 8 emotions: Anger, Contempt, Disgust, Fear, Happiness, Neutral, Sadness, Surprise
   - Based on EmotiEffLib (Sber AI Lab, MIT license)
   - iOS 17+ target

2. **Rewrote FacialEmotionService.swift** - Full implementation replacing placeholder
   - Vision framework for face detection
   - CoreML for emotion classification
   - Frame extraction every 7 seconds

3. **Updated TemporalAnalysisService** - Integrated facial emotions
   - Combines facial (60%) + text (40%) emotions
   - Fallback to text-only if facial fails

## HeyGen Integration (2026-02-19)
- **API key:** `~/.clawdbot/credentials/heygen-api-key`
- **Plan:** Pro API $99/mo, ~5,950 credits
- **Avatar group v2:** `5c1e41862ca84cd1b4b45f3463e91409` (straight headshot, trained)
- **Lily audio asset:** `f4545cfa8b8e4f4fbbf9752163416079`
- **API quirk:** `talking_photo_id` goes at character level, NOT nested under talking_photo object
- **Streaming Avatar works on Pro plan** — WebRTC session confirmed working
- **Next:** Build live avatar web app pulling from cloud brain

## Cloud Brain Architecture
- **GitHub repo:** `derickdahl/l3-memory` (private) — central source of truth
- **Voice bridge:** `l3-voice-bridge.vercel.app` — reads from GitHub repo
- **Local:** `~/clawd/` on Mac Studio — primary working copy
- **Status (2026-02-19):** GitHub repo ~2 weeks behind local. NEEDS SYNC before building live avatar.
- **All instances must pull from same brain** — text, voice, live avatar, Teams bot

## Sonance Colleagues on OpenClaw
- **Aron Mckay** — "ClawOne" instance, setting up M365 + Asana
- **Josh Blanken** — "Jarvis" instance, setting up Asana

### Status
App needs Xcode build test. Derick needs to:
1. Add EmotionClassifier.mlpackage to Xcode project
2. Build and fix any compile errors
3. Test on device

### Also Discussed
- Business models for passive income ($1,400/day goal)
- Optamistic as the chosen path (validated through first-principles)
- Executive OS updates (Supabase response tracking)
- Expense reconciliation (Vueling flight not on statement)
