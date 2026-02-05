# Development Stack Configuration

**Standard stack for all web projects (unless iOS):**
- Next.js (frontend/backend)
- Supabase (database)
- GitHub (version control)
- Vercel (hosting)
- Sonance Brand MCP (branding)

## Credentials Location

| Service | Credential File |
|---------|-----------------|
| GitHub | `~/.clawdbot/credentials/github-token` |
| Supabase (Business) | `~/.clawdbot/credentials/supabase-token` |
| Supabase (Personal) | `~/.clawdbot/credentials/supabase-token-personal` |
| Vercel Token | `~/.clawdbot/credentials/vercel-token` |
| Vercel Team ID | `~/.clawdbot/credentials/vercel-team-id` |

## Which Supabase to Use

| Project Type | Supabase Account |
|--------------|------------------|
| Business/Work (Sonance) | Business (`supabase-token`) |
| Personal projects | Personal (`supabase-token-personal`) |

**Examples:**
- Executive OS → Business
- StoryboardAI → Personal

## Sonance Brand MCP

To initialize in a project:
```bash
npx sonance-brand-mcp@latest --init-code
```

Creates `.mcp.json` with brand assets, components, and guidelines.

## Environment Setup

```bash
# GitHub
export GH_TOKEN=$(cat ~/.clawdbot/credentials/github-token)

# Vercel
export VERCEL_TOKEN=$(cat ~/.clawdbot/credentials/vercel-token)

# Supabase (Business)
export SUPABASE_ACCESS_TOKEN=$(cat ~/.clawdbot/credentials/supabase-token)

# Supabase (Personal)
export SUPABASE_ACCESS_TOKEN=$(cat ~/.clawdbot/credentials/supabase-token-personal)
```

## Project Creation Workflow

1. Create GitHub repo: `gh repo create <name> --private`
2. Create Supabase project: `supabase projects create <name>`
3. Scaffold Next.js: `npx create-next-app@latest`
4. Init Sonance branding: `npx sonance-brand-mcp@latest --init-code`
5. Deploy to Vercel: `vercel --yes`

---

*Last updated: 2026-01-29*
