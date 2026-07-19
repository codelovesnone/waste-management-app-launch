# Technical Plan — Base44 Store Submission & Future Native Rebuild

**Product:** Apex Connect  
**Near-term goal (≤ 60 days):** Ship store-ready iOS and Android builds from the current Base44 application path  
**Longer-term goal:** Evaluate and plan a native (or cross-native) rebuild for scale, performance, and nationwide expansion  
**Constraint:** This repository is a launch command center. Do not add fake production application code to `src/`.

---

## 1. Strategy summary

```text
Now (Days 1–60)          Later (post-launch)
─────────────────────    ──────────────────────────────
Base44 product    →      Stabilize store presence
Store packaging   →      Harden ops + monitoring
Public listings   →      Native / cross-native rebuild
                          for scale & differentiation
```

**Principle:** Separate **distribution** (getting into App Store & Play) from **re-platforming** (rewriting the client). Attempting both in 60 days is high risk for a client-facing launch.

---

## 2. Current system (working model)

| Layer | Current state | Notes |
|-------|---------------|-------|
| Client app | Base44-built experience | Source of truth until export/rebuild |
| Backend / data | Base44-managed (verify) | Confirm environments, backups, rate limits |
| Identity | App auth via Base44 (verify methods) | Email/password vs magic link vs other |
| Domain logic | Property / location association; shared visibility; complaint routing | Launch-critical correctness |
| This git repo | Docs + assets only | `src/` reserved for future real code |

Engineering must replace “verify” items with facts once Base44 access is granted (`current-app-audit.md`).

---

## 3. 60-day technical objective

Deliver:

1. An **iOS binary** acceptable to App Store Connect  
2. An **Android App Bundle (AAB)** acceptable to Play Console  
3. Builds pointed at **production** (or a client-approved production-equivalent) configuration  
4. A repeatable process to ship **hotfix versions** after launch  
5. Documentation sufficient for handoff  

Non-goals for this window:

- Full rewrite in Swift/Kotlin/React Native/Flutter  
- Large feature expansion for nationwide markets  
- Replacing Base44 backend unless required for store compliance  

---

## 4. Base44 → store packaging plan

### 4.1 Discovery tasks (Week 1)

- [ ] Inventory Base44 mobile / PWA / wrapper capabilities for this project  
- [ ] Confirm whether Base44 provides direct App Store / Play packaging or requires a standard WebView / Capacitor / similar shell  
- [ ] Identify signing requirements (Apple certificates, Play app signing)  
- [ ] Confirm environment variables / API bases for staging vs production  
- [ ] List embedded SDKs that affect privacy disclosures  

### 4.2 Target packaging options (decide by Day 14)

| Option | When to choose | Pros | Cons |
|--------|----------------|------|------|
| **A. Native export / Base44 store pipeline** | Base44 fully supports store builds | Fastest path; least custom code | Dependent on platform limits |
| **B. Thin native shell (WebView / Capacitor-class)** | Web app solid; store needs a binary container | Controllable signing & store metadata | Must meet store quality bars for wrapped apps |
| **C. Hybrid emergency path** | A/B blocked | Keeps timeline alive | Scope carefully; avoid half-rewrites |

**Decision gate (Day 14):** Document the chosen option in the Decision log (`client-meeting-notes.md`) and update the README status table.

### 4.3 Identity & identifiers

Reserve and document:

| Platform | Identifier | Example pattern (final TBD) |
|----------|------------|-------------------------------|
| iOS | Bundle ID | `com.<company>.apexconnect` |
| Android | Application ID | `com.<company>.apexconnect` |
| Apple | SKU / app name in ASC | Client-approved |
| Google | Play app name | Client-approved |

Align identifiers with the final public name from `open-questions.md` (Q6).

### 4.4 Signing & release engineering

**iOS**

- Organization team in Apple Developer  
- App ID + capabilities (Push, Associated Domains, etc. only if used)  
- Archive → upload to App Store Connect  
- TestFlight internal testing before review  

**Android**

- Create upload key / use Play App Signing  
- Build AAB (not APK) for Play  
- Internal testing track → closed → production (or staged)  

**Versioning**

- Propose: `MAJOR.MINOR.PATCH` marketing version  
- Monotonic build numbers / version codes for each store upload  
- Document in release notes who bumps what  

### 4.5 Configuration matrix

| Config | Staging | Production |
|--------|---------|------------|
| API / Base44 env | TBD | TBD |
| Feature flags | Prefer stable subset | Launch freeze |
| Logging | Verbose OK | Privacy-safe |
| Demo accounts | Yes | Reviewer-only / support-controlled |

Never commit secrets (see root `.gitignore`).

### 4.6 Store compliance engineering checklist

- [ ] App launches to usable UI on mid-tier devices  
- [ ] No broken links or placeholder “lorem” screens in the release build  
- [ ] Login required → reviewer credentials work on the submitted build  
- [ ] Account deletion path implemented or clearly linked  
- [ ] Privacy Policy accessible  
- [ ] Permission prompts (camera, photos, location) only when needed and explained  
- [ ] Data safety / App Privacy answers match reality  

---

## 5. QA technical scope (launch)

### Critical path test matrix

| Flow | Tenant | Property staff | Notes |
|------|--------|----------------|-------|
| Sign in / out | ✓ | ✓ | |
| View correct property context | ✓ | ✓ | Isolation tests |
| Submit complaint | ✓ | ✓ if applicable | Include photo if supported |
| See routed complaint | ✓ | ✓ | Correct location only |
| Unauthorized property access | Expect deny | Expect deny | Security |

### Devices (minimum)

- One recent iPhone + one older supported iPhone  
- One recent Android phone + one mid-range Android  
- OS versions: document minimum after Base44 constraints known  

### Environments

- Smoke on staging, sign-off on production RC  

---

## 6. Monitoring & operations (launch week)

| Concern | Approach |
|---------|----------|
| Crashes | Enable whatever crash reporting Base44 supports; otherwise add a lightweight tool post-access |
| Auth failures | Watch support inbox + backend logs |
| Routing errors | Client ops validation with GA/AL properties |
| Store reviews | Daily check Day 0–7 |
| Hotfix | Keep packaging pipeline ready for 48-hour turnaround |

Document on-call / owner names in meeting notes before go-live.

---

## 7. Future native rebuild considerations

The store launch is **not** the end state. A native or serious cross-platform rebuild should be evaluated after the product is publicly distributed and usage patterns are clearer.

### 7.1 Why consider a rebuild later

- Greater control over UX performance and offline behavior  
- Cleaner role-based security boundaries and audited access control  
- Independent release cadence from Base44 platform constraints  
- Better foundation for **nationwide** multi-tenant scale  
- Stronger differentiation (driver ops, richer notifications, deeper property tools)  

### 7.2 Candidate directions (decision later)

| Approach | Fits if… |
|----------|----------|
| React Native / Expo | One team, shared UI, strong JS skills, need speed |
| Flutter | Desire for cohesive UI toolkit and single codebase |
| Native Swift + Kotlin | Maximum platform quality; higher cost |
| Incremental rewrite | Keep Base44 backend; replace client modules over time |

**Recommendation posture:** Do not pick a stack in this document until post-launch metrics and budget are clear. Capture requirements first.

### 7.3 Rebuild prerequisites (post-60-day)

1. Stable store presence and support process  
2. Written product spec for roles, visibility, and complaint lifecycle  
3. API / data contract clarity (whether staying on Base44 backend or migrating)  
4. Design system and brand kit  
5. Test fixtures for multi-property scenarios  
6. Security review of shared-visibility model  
7. Migration plan for existing users and devices already installed from stores  

### 7.4 What to preserve from v1

- Property / location as the routing key for complaints  
- Shared visibility rules trusted by complexes and tenants  
- Store listings, bundle IDs, and brand equity (avoid breaking installs if possible)  
- Analytics definitions for complaint funnel metrics  

### 7.5 What to improve in a rebuild

- Explicit RBAC and audit trails  
- Faster complaint triage workflows for ops  
- Robust push notification preferences  
- Offline-friendly draft complaints  
- Multi-state / nationwide onboarding tooling  
- Automated regression tests around isolation rules  

---

## 8. Suggested technical milestones (aligned to roadmap)

| Milestone | Day | Engineering outcome |
|-----------|-----|---------------------|
| T0 Access | 1–7 | Base44 access; packaging spike started |
| T1 Path freeze | 14 | Option A/B/C chosen |
| T2 Internal builds | 21–28 | TestFlight + Play internal |
| T3 RC | 35 | Store-ready binaries + asset freeze |
| T4 Submit | 36–42 | Both stores submitted |
| T5 Live | 51–60 | Production release + hotfix readiness |
| T6 Rebuild brief | Post-60 | One-pager recommendation for client |

---

## 9. Definition of done (technical — 60-day launch)

- [ ] Reproducible iOS and Android store builds documented  
- [ ] Signing and Play App Signing configured under client-owned accounts  
- [ ] Critical path QA signed off on RC  
- [ ] Privacy / Data safety inputs completed from a real data inventory  
- [ ] Reviewer demo accounts validated on the submitted build  
- [ ] Hotfix runbook written (who builds, who submits, who notifies client)  
- [ ] Native rebuild considerations reviewed with client (timing only—not execution)

---

## 10. Open technical dependencies

Tracked in detail in [`open-questions.md`](open-questions.md):

- Base44 access and packaging capability (Q3, Q7)  
- Auth model, deletion, SDKs (Q8–Q11)  
- Push notifications scope (Q16)  

Until those close, estimates for binary readiness remain provisional.

---

## 11. Document ownership

| Section | Owner |
|---------|--------|
| Packaging decision | Engineering lead |
| Signing & store upload | Engineering |
| Privacy data inventory | Engineering + client |
| Rebuild recommendation | Delivery + engineering (post-launch) |

Update this plan when the Day 14 packaging decision is made—replace options with a single chosen path and concrete build commands/runbook links as they become real.
