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
- **Optamistic** — self-improvement platform (Replit + Supabase)
- **Trust Me, Bro** — screenplay about three brothers finding estranged father
- **DreamLight** — AI dream analysis app concept
- **South Shores Worship** — church album to record

---

## MTP (Massive Transformative Purpose)

*To be a storyteller who helps humanity understand how to create a brighter, hopeful vision of the future.*

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
