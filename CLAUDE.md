# CLAUDE.md — Jupiter Golf Week

This file is read automatically by Claude Code at the start of every session.
Follow these rules for all work in this project.

## Cross-Project Context
Before starting work, read the workspace Project Registry for relationship context:
`C:\Users\brian\projects\PROJECT_REGISTRY.md`
Static site backed by the **Neon Data API** (Neon project `icy-dawn-94906269`) for score sync. Supabase is retired — do not reintroduce it.

---

## What This Site Is
Single-page event site for a golf week event.

## Stack
- Static HTML/CSS/JS
- GitHub Pages
- Neon Data API (PostgREST-compatible) via `@neondatabase/neon-js` (loaded from esm.sh) with Neon Auth anonymous tokens
  - Table `golf_scores` (one row per course: jupiter, bears, medalist)
  - Anonymous role: SELECT, and UPDATE on (scores, notes, handicap, updated_at) only — no INSERT/DELETE
  - Data API: `https://ep-withered-night-b76axl4q.apirest.c-13.us-east-1.aws.neon.tech/neondb/rest/v1`
  - Auth: `https://ep-withered-night-b76axl4q.neonauth.c-13.us-east-1.aws.neon.tech/neondb/auth`
- localStorage-first load with offline fallback; scores sync to Neon only via the explicit Save button

## Key Files
- `index.html` — Full site (single page)

## Deployment
Push to `main` → GitHub Pages auto-deploys.

## Project Context (migrated from claude.ai 2026-05-25)
The original claude.ai "Golf Visit" Project has been retired. Memory snapshot at `research/claude_ai_project_memory.md` documents an earlier richer feature set (Supabase sync, NWS weather API, hybrid persistence, analytics). **Drift note:** score sync has since moved from Supabase to Neon (2026-10-06); weather/analytics details in the snapshot may still be stale. Trust the repo. Archive preserved in case the richer version is ever revived. 2 setup guide knowledge files not preserved (duplicated by Cowork skills). 1 old conversation not preserved.
