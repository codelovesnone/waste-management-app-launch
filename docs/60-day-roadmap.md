# 60-Day App Store Launch Roadmap

**Product:** Apex Connect  
**Goal:** Public availability on Apple App Store and Google Play  
**Window:** 60 calendar days from project kickoff  
**Approach:** Ship the current Base44 product to the stores first; defer a full native rebuild to a post-launch phase

---

## Timeline overview

| Phase | Days | Theme | Outcome |
|-------|------|--------|---------|
| 1 — Foundation | 1–14 | Access, audit, accounts | Unblocked delivery + clear gap list |
| 2 — Packaging | 15–35 | Builds, assets, QA | Store-ready binaries + listing drafts |
| 3 — Submission | 36–50 | Review, fixes, compliance | Apps in review / approved |
| 4 — Launch | 51–60 | Soft launch, monitor, handoff | Live listings + ops runbook |

Target stores: **iOS (App Store)** and **Android (Google Play)** in the same window. Android often clears faster; plan for Apple review buffer.

---

## Phase 1 — Foundation (Days 1–14)

### Objectives

- Confirm product scope for v1 store release  
- Obtain all required accounts and Base44 access  
- Finish discovery audit and freeze “must ship” vs “later”  
- Align on app name, bundle IDs, and legal URLs  

### Week 1 (Days 1–7)

| Day | Workstream | Deliverable | Owner |
|-----|------------|-------------|--------|
| 1–2 | Kickoff & access requests | Invites sent for Apple, Google, Base44 | Client + delivery |
| 1–3 | Product walkthrough | Recorded flows: auth, property visibility, complaints | Delivery |
| 2–5 | Current app audit | Gaps logged in `current-app-audit.md` | Engineering |
| 3–7 | Legal & brand intake | Privacy Policy / Terms / support URL draft or live links | Client |
| 5–7 | Open questions triage | Prioritized list in `open-questions.md` | Delivery |

### Week 2 (Days 8–14)

| Day | Workstream | Deliverable | Owner |
|-----|------------|-------------|--------|
| 8–10 | Store account setup | Apple org membership active; Play Console created | Client |
| 8–12 | Technical path decision | Confirmed Base44 → store packaging approach | Engineering |
| 10–14 | Identity & naming | Final display name, bundle ID / application ID | Client + eng |
| 12–14 | Phase 1 gate review | Go / no-go for packaging phase | All |

### Phase 1 exit criteria

- [ ] Base44 admin access verified  
- [ ] Apple Developer Program membership active (organization preferred)  
- [ ] Google Play Console accessible with a developer account  
- [ ] Privacy Policy URL live and linkable  
- [ ] Support email / URL confirmed  
- [ ] Audit complete enough to start builds  
- [ ] Critical open questions answered or explicitly deferred  

---

## Phase 2 — Packaging & QA (Days 15–35)

### Objectives

- Produce installable iOS and Android builds from the Base44 path  
- Assemble store creatives and metadata  
- Complete functional QA against launch-critical flows  
- Address store policy risks before first submission  

### Week 3 (Days 15–21)

| Focus | Tasks |
|-------|--------|
| Builds | Configure Base44 (or wrapper) for iOS + Android store targets |
| Branding | App icon (all required sizes), splash, brand colors |
| Metadata | Draft short/long descriptions, keywords, categories |
| Compliance | Age rating questionnaire inputs; data safety / privacy nutrition labels draft |

### Week 4 (Days 22–28)

| Focus | Tasks |
|-------|--------|
| Screenshots | Capture iPhone and Android phone frames (tablet optional if targeting tablets) |
| Internal testing | TestFlight internal + Play internal testing track |
| QA script | Sign-in, shared account visibility, property/location routing, complaint submit/view |
| Bug triage | P0/P1 fixes only for store v1 |

### Week 5 (Days 29–35)

| Focus | Tasks |
|-------|--------|
| External testing | Closed testing (Play) / external TestFlight if needed |
| Listing polish | Final copy approved by client |
| Asset freeze | Locked files in `assets/app-store-assets/` |
| Pre-submission review | Walk `app-store-launch-checklist.md` end-to-end |

### Phase 2 exit criteria

- [ ] Release candidate builds on both platforms  
- [ ] Internal testers signed off on critical paths  
- [ ] Store listing assets complete and approved  
- [ ] Privacy labels / Data safety forms drafted with client input  
- [ ] No open P0 defects  

---

## Phase 3 — Submission & Review (Days 36–50)

### Objectives

- Submit to Apple and Google  
- Respond to review feedback within 24–48 hours  
- Clear policy or binary rejections  

### Week 6 (Days 36–42)

| Platform | Actions |
|----------|---------|
| Google Play | Upload AAB, complete Data safety, content rating, store listing → submit to production or staged rollout |
| Apple App Store | Upload build via App Store Connect, complete App Privacy, review notes, screenshots → submit for review |
| Both | Provide demo credentials for reviewers if login is required |

### Week 7 (Days 43–50)

| Focus | Tasks |
|-------|--------|
| Review response | Answer Apple/Google questions; resubmit if needed |
| Hotfixes | Ship review-blocking fixes only |
| Soft-launch prep | Confirm production config, analytics, support inbox monitoring |
| Comms | Client-approved launch announcement copy (optional) |

### Phase 3 exit criteria

- [ ] Google Play: approved for production (or staged % agreed with client)  
- [ ] Apple: Ready for Sale or Pending Developer Release with client go-ahead  
- [ ] Reviewer demo account still valid  
- [ ] Support channel staffed for launch week  

---

## Phase 4 — Launch & Stabilize (Days 51–60)

### Objectives

- Make the app publicly available  
- Monitor crashes, auth, and complaint-routing issues  
- Hand off an update / ops cadence  

### Days 51–55 — Go live

- Release on both stores (coordinate timing if brand wants same-day)  
- Verify public listing pages and install from cold store search  
- Smoke-test production against Georgia / Alabama property scenarios  
- Monitor Base44 / backend health and store crash reports  

### Days 56–60 — Stabilize & handoff

- Triage early user feedback  
- Document known limitations for nationwide expansion later  
- Schedule first post-launch update window  
- Capture “native rebuild” recommendations in `technical-plan.md` for Phase 2 product work  

### Phase 4 exit criteria

- [ ] Public App Store + Play listings live  
- [ ] Support process confirmed  
- [ ] Launch retrospective notes filed  
- [ ] Post-60-day backlog prioritized (native rebuild, multi-state expansion, etc.)  

---

## Critical path dependencies

These items can slip the entire 60-day window if delayed:

1. **Organization Apple Developer enrollment** (can take days to weeks for D-U-N-S / verification)  
2. **Privacy Policy & Terms** live on a public URL  
3. **Base44 export / mobile packaging capability** confirmed working  
4. **Client approval cycles** on name, icon, and store copy  
5. **Login-required demo account** for App Review  

Start Apple organization enrollment on Day 1.

---

## Scope for the 60-day release

### In scope

- Store presence for the current Apex Connect experience  
- Core tenant / property shared visibility for complaint routing  
- Branding and listing quality suitable for a professional B2B2C utility app  
- Basic crash / error monitoring visibility  
- Documentation and handoff for ongoing updates  

### Out of scope (post-launch / native rebuild track)

- Full rewrite in Swift / Kotlin / React Native / Flutter  
- Nationwide multi-tenant marketplace expansion features  
- Major UX redesign  
- New payment systems unless already live in Base44  
- Deep offline-first architecture  

See [`technical-plan.md`](technical-plan.md) for how the rebuild track relates to this launch.

---

## Risk register (launch window)

| Risk | Impact | Mitigation |
|------|--------|------------|
| Apple org account delayed | High | Start Day 1; use individual account only as last resort with migration plan |
| Base44 cannot produce store builds | High | Validate in Week 1; define wrapper/fallback by Day 14 |
| Privacy Policy not ready | High | Use counsel template early; block submission without URL |
| Review rejection (incomplete app / login) | Medium | Demo account + review notes; trim unfinished features from listing |
| Shared-account model confuses reviewers | Medium | Clear review notes explaining property/tenant visibility |
| Asset approval lag | Medium | Freeze design by Day 28; client SLA 48h on reviews |

---

## Cadence & governance

- **Twice-weekly status** (async or 20-min call): blockers, checklist %, next 72 hours  
- **Single status source:** this repo (`README.md` status table + this roadmap)  
- **Decision log:** [`client-meeting-notes.md`](client-meeting-notes.md)  
- **Blockers list:** [`open-questions.md`](open-questions.md)  

---

## Milestone checklist (summary)

- [ ] **M1 (Day 14):** Accounts + audit complete  
- [ ] **M2 (Day 35):** RC builds + assets frozen  
- [ ] **M3 (Day 50):** Both stores approved or in final resubmit  
- [ ] **M4 (Day 60):** Public launch + ops handoff  

Adjust dates in this file when kickoff day is formally set; keep relative day numbers intact for planning clarity.
