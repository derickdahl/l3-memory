# Context Management Strategy

**Problem:** Context window overflow (170k+ tokens) causing memory loss and request failures.

## New Approach

### 1. Lean Core Files
- **TOOLS.md** → Compress to essentials only, move details to memory/
- **AGENTS.md** → Keep core workflow, move examples to separate files
- **Memory files** → Target <1k per daily file, summarize weekly

### 2. Smart Memory Retrieval
- Use `memory_search` first, then `memory_get` for specific lines only
- Never load full memory files unless essential
- Create topic-specific memory files instead of monster daily logs

### 3. Session Context Hygiene
- Track token usage (aim for <150k input)
- Create "context reset" checkpoints when approaching limits
- Summarize long conversations into discrete memory entries

### 4. File Structure Changes
```
memory/
├── 2026-02-XX.md (daily - keep short)
├── topics/
│   ├── barcelona-2026.md
│   ├── ise-2026.md
│   ├── sonance-tech-support.md
│   └── executive-os.md
├── summaries/
│   └── 2026-02-week1.md
└── archives/
    └── old-context-files/
```

## Immediate Actions
1. Compress TOOLS.md to <2k tokens
2. Create topic-specific memory files for Barcelona week
3. Document Sonance Tech Support agent details
4. Set up weekly summary workflow

**Goal:** Maintain rich memory while staying under 150k context tokens.