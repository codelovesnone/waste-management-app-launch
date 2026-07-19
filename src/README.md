# `src/` — Application Source (Reserved)

This directory is intentionally empty of application code.

## Why this folder exists

The Apex Connect launch repository is a **documentation and command-center hub** for the 60-day App Store / Google Play effort. The live product currently runs on **Base44**. Until the client and delivery team deliberately place a real export, wrapper project, or native rebuild here, `src/` remains a placeholder so the repo structure is ready without implying a fake codebase.

## Do not

- Add sample apps, stub screens, or generated boilerplate presented as production code  
- Commit secrets, API keys, or Base44 credentials  
- Treat this folder as the source of truth for the live product today  

## When code should land here

Appropriate future contents (examples):

| Contents | When |
|----------|------|
| Base44 export or sync’d web assets | If the packaging path needs versioned static/web output |
| Thin native shell (e.g. Capacitor-class wrapper) | If Option B in `docs/technical-plan.md` is selected |
| Native / cross-platform app | Post-launch rebuild track |
| Shared scripts for store packaging | When a real, repeatable build pipeline exists |

## Related docs

- Launch plan: [`../docs/60-day-roadmap.md`](../docs/60-day-roadmap.md)  
- Technical approach: [`../docs/technical-plan.md`](../docs/technical-plan.md)  
- Current product audit: [`../docs/current-app-audit.md`](../docs/current-app-audit.md)  
- Repo overview: [`../README.md`](../README.md)  

## Status

**No production application source in this repository yet.**  
Base44 remains the active product platform for the store launch window.
