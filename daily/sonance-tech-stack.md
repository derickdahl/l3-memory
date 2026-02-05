# Sonance Internal App Development Stack

*Context for building internal custom apps at Sonance*

## Architecture (Bottom to Top)

### 1. Data Layer
- **Azure Databricks** - Data lakehouse (foundational data)
- **ERD Layer** - Entity-relationship layer on top of lakehouse

### 2. Integration Layer
- **Cortex Layer** - Tracks all MCPs and integrations
- Provides unified access to data and services

### 3. UI/UX Layer
- **Brand Guidelines MCP** - Sonance brand standards
- **Component Library MCP** - Reusable UI components
- Ensures consistent look/feel across all internal apps

### 4. Hosting & Data
- **Vercel** - App hosting / deployment
- **Supabase** - App-level data (auth, database, storage)

### 5. Code Management
- **GitHub** - Source code repositories

### 6. Distribution
- **Teams App Store** - Official release channel for business users
- Internal users discover and install apps here

## App Development Flow

1. Discovery meeting (tagged with `(APP)`)
2. Process transcript → Generate PRD
3. Design with component library
4. Build connecting to ERD/Cortex as needed
5. Store app data in Supabase
6. Deploy to Vercel
7. Push code to GitHub
8. Package and release to Teams App Store

## Questions to Clarify
- [ ] Access to Cortex layer documentation?
- [ ] Component library MCP - where are the docs/examples?
- [ ] ERD layer - how to query/access?
- [ ] Teams App Store - packaging requirements?
- [ ] GitHub org - which org/repos to use?

---

*Added 2026-01-27*
