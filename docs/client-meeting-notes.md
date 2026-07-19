# Client Meeting Notes

**Product:** Apex Connect — App Store & Google Play launch  
**How to use:** Add a new dated section after every client or stakeholder session. Capture decisions, owners, and due dates—not full transcripts.

---

## Meeting log template

Copy this block for each new session:

```markdown
### YYYY-MM-DD — <Meeting title>

**Attendees:**  
**Facilitator:**  

#### Agenda
- 

#### Decisions
- 

#### Action items
| Action | Owner | Due | Status |
|--------|-------|-----|--------|
| | | | Open |

#### Notes
- 

#### Open questions raised
- Link or copy into `open-questions.md`
```

---

## Project kickoff context (baseline)

### 2026-07 — Engagement framing (working notes)

**Attendees:** Client stakeholders · Delivery team  
**Status:** Initial discovery / repository stand-up  

#### Confirmed context

- Client operates a **waste management** business  
- Current application built on **Base44**  
- Goal: launch to **Apple App Store** and **Google Play** within **60 days**  
- Product supports **tenants** and **apartment complexes** with **shared account visibility** so complaints route to the correct **property / location**  
- Current operating footprint: **Georgia** and **Alabama**  
- Strategic intent: **nationwide expansion** after a stable launch  

#### Working assumptions (pending formal confirmation)

- Store launch will use the **existing Base44 product path**, not a full native rewrite in the 60-day window  
- A future **native rebuild** remains on the roadmap (see `technical-plan.md`)  
- Public store listings should present a professional B2B2C utility experience appropriate for property residents and managers  

#### Decisions

- Establish this repository as the **launch command center** and documentation hub  
- Keep `src/` empty of fake production code until a real export or rebuild begins  

#### Action items

| Action | Owner | Due | Status |
|--------|-------|-----|--------|
| Grant Base44 project access to delivery team | Client | ASAP | Open |
| Start Apple Developer Program (Organization) enrollment | Client | Week 1 | Open |
| Create / share Google Play Console access | Client | Week 1 | Open |
| Provide Privacy Policy + Terms URLs (or counsel draft timeline) | Client | Week 1–2 | Open |
| Confirm public app display name and brand assets | Client | Week 1–2 | Open |
| Schedule recurring status cadence (2× weekly) | Delivery lead | Week 1 | Open |
| Complete first-pass app audit | Engineering | Week 1–2 | Open |

#### Notes

- Nationwide expansion is a **growth narrative**, not a promise that every U.S. market is live on day one of store launch  
- Complaint routing accuracy and property isolation are launch-critical trust requirements  

#### Open questions raised

- See [`open-questions.md`](open-questions.md) for the full prioritized list  

---

## Decision log (running)

Record only durable decisions here for quick scanning.

| Date | Decision | Decided by | Implications |
|------|----------|------------|--------------|
| 2026-07 | Repo is documentation / launch hub; no fake app code | Delivery team | `src/` remains placeholder |
| 2026-07 | 60-day goal targets both Apple and Google | Client context | Parallel store workstreams |
| TBD | Final public app name | Client | Bundle ID, listing, icon text |
| TBD | Base44 packaging approach for iOS/Android | Engineering + client | Build pipeline & timeline |
| TBD | Soft launch (staged) vs full public same day | Client | Play rollout %; Apple release method |

---

## Stakeholder map

| Stakeholder | Interest | Needed from them |
|-------------|----------|------------------|
| Business owner / exec sponsor | Store presence, brand trust, expansion story | Approvals, Apple/Google accounts |
| Operations lead | Complaint routing accuracy | Test scenarios, support process |
| Property / client success | Resident and complex experience | Feedback on visibility rules |
| Legal / compliance | Privacy, terms, data practices | Policy URLs, deletion policy |
| Delivery / engineering | Builds, QA, submission | Access, timely answers |

---

## Communication norms

- **Source of truth:** this repository  
- **Blockers:** logged in `open-questions.md` with owner + due date  
- **Status:** update root `README.md` status table after each major milestone  
- **Approvals:** name, icon, screenshots, and store copy require explicit client OK before submission  

---

## Upcoming sessions (suggested)

1. **Access & legal workshop** — accounts, privacy, support contacts  
2. **Product freeze review** — what reviewers will see in v1  
3. **Brand & listing review** — icon, screenshots, descriptions  
4. **Pre-submission gate** — checklist walkthrough  
5. **Launch readiness** — support coverage, rollout plan, comms  

Add dated notes under this file as sessions occur.
