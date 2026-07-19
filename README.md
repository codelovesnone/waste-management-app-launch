# Apex Connect — App Store Launch Command Center

**Client:** Waste management operator (Georgia & Alabama, nationwide expansion planned)  
**Platform today:** Base44  
**Target:** Apple App Store + Google Play within **60 days**  
**Repo purpose:** Launch documentation hub — not a production application codebase

---

## Mission

Publish Apex Connect to the public app stores so tenants, property managers, and apartment complexes can use the product from iOS and Android devices without relying on a web-only workflow. This repository is the single source of truth for launch planning, discovery, store readiness, open client questions, required access, and the technical path from Base44 to store submission.

---

## Current status

| Area | Status | Notes |
|------|--------|--------|
| Discovery & audit | In progress | Baseline product understanding captured; deeper Base44 / account access still needed |
| 60-day roadmap | Drafted | Phased plan from kickoff through store go-live |
| App Store readiness | Not started | Apple Developer + Google Play Console access required |
| Store assets | Pending client | Logos, screenshots, privacy policy, support URLs |
| Technical plan | Drafted | Base44 export / wrapper / submission path + native rebuild horizon |
| Client decisions | Open | See [`docs/open-questions.md`](docs/open-questions.md) |

**Last updated:** July 2026

---

## Product context

Apex Connect supports waste-management operations for multi-unit properties:

- **Tenants and apartment complexes** share account visibility where appropriate
- **Complaints and service issues** can be routed to the correct property / location
- **Current markets:** Georgia and Alabama
- **Growth intent:** Nationwide expansion after a stable store launch

The existing product lives on **Base44**. The 60-day goal is store presence with the current product path—not a full native rewrite in this window.

---

## Repository map

```text
.
├── README.md                          ← You are here
├── .gitignore
├── docs/
│   ├── 60-day-roadmap.md              ← Week-by-week launch plan
│   ├── app-store-launch-checklist.md  ← Apple + Google readiness checklist
│   ├── current-app-audit.md           ← Discovery findings & gaps
│   ├── client-meeting-notes.md        ← Working notes from client sessions
│   ├── open-questions.md              ← Decisions & access still needed
│   └── technical-plan.md              ← Base44 submission + native rebuild notes
├── assets/
│   ├── screenshots/                   ← Device screenshots for store listings
│   ├── logos/                         ← Brand marks & app icons source
│   └── app-store-assets/              ← Final store creatives & metadata drafts
└── src/
    └── README.md                      ← Placeholder for future app source (none yet)
```

---

## Documentation index

| Document | Audience | Purpose |
|----------|----------|---------|
| [60-day roadmap](docs/60-day-roadmap.md) | Client + delivery team | Phased plan from Day 0 → store live |
| [App store launch checklist](docs/app-store-launch-checklist.md) | Delivery team | Apple & Google submission requirements |
| [Current app audit](docs/current-app-audit.md) | Delivery team | What exists today, what’s missing |
| [Client meeting notes](docs/client-meeting-notes.md) | Shared | Decisions, owners, follow-ups |
| [Open questions](docs/open-questions.md) | Client | Blockers and decisions needed |
| [Technical plan](docs/technical-plan.md) | Engineering | Base44 path + future native rebuild |

---

## What we need from the client (priority)

1. **Apple Developer Program** account (organization) — admin or developer invite  
2. **Google Play Console** account — admin or release manager invite  
3. **Base44** project access (export, build, domain, and admin settings)  
4. **Legal / policy URLs:** Privacy Policy, Terms of Use, support email / URL  
5. **Brand assets:** App name confirmation, icon, logo variants, brand colors  
6. **Store copy approval:** Short description, long description, keywords, category  
7. Answers to items in [`docs/open-questions.md`](docs/open-questions.md)

Drop finalized creatives into:

- `assets/logos/`
- `assets/screenshots/`
- `assets/app-store-assets/`

---

## Success criteria (60-day launch)

- [ ] Apex Connect available on the **Apple App Store** (public or approved TestFlight → production)  
- [ ] Apex Connect available on **Google Play** (production track)  
- [ ] Store listings complete with approved branding, screenshots, and privacy disclosures  
- [ ] Core flows verified: sign-in, property/location context, complaint routing visibility  
- [ ] Support contact and privacy policy linked from both stores  
- [ ] Post-launch monitoring and update process documented  

---

## Working principles

- This repo is a **launch command center**. Prefer clear status, owners, and dates over speculative code.  
- Do **not** treat `src/` as a production app until a deliberate rebuild or export lands here.  
- Keep client-facing docs accurate; mark unknowns as unknowns.  
- Separate **store launch on Base44** from a later **native rebuild**—both are planned, different timelines.

---

## Next actions

1. Complete Base44 access and current-app audit gaps → [`docs/current-app-audit.md`](docs/current-app-audit.md)  
2. Resolve open client questions → [`docs/open-questions.md`](docs/open-questions.md)  
3. Stand up developer accounts and begin checklist → [`docs/app-store-launch-checklist.md`](docs/app-store-launch-checklist.md)  
4. Execute Week 1–2 of the roadmap → [`docs/60-day-roadmap.md`](docs/60-day-roadmap.md)

---

## Contact & ownership

| Role | Responsibility |
|------|----------------|
| Client stakeholders | Brand, legal URLs, store accounts, product decisions |
| Delivery / product lead | Roadmap, status, checklist completion |
| Engineering | Base44 build path, store packaging, QA |
| Design / brand | Icons, screenshots, listing creatives |

Update this README whenever status, owners, or launch date assumptions change.
