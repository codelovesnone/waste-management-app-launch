# Open Questions — Client Decisions & Access

**Product:** Apex Connect  
**Purpose:** Track everything still needed from the client or still undecided before a clean App Store / Google Play submission.  
**Rule:** Every item has an owner, priority, and status. Move resolved items to the Resolved section (do not delete history).

**Priority key:** `P0` blocks launch timeline · `P1` blocks quality/compliance · `P2` nice to clarify  

---

## Summary

| Priority | Open | Blocked on client access | Needs decision |
|----------|------|--------------------------|----------------|
| P0 | See list below | Apple, Google, Base44, legal URLs | App name, packaging path confirmation |
| P1 | Privacy data inventory, account deletion, demo users | Brand assets, support process | Categories, rollout strategy |
| P2 | Nationwide messaging, analytics depth | Optional video | Post-launch native rebuild timing |

---

## P0 — Launch blockers

### Q1. Apple Developer account

- **Question:** Will the client enroll an **Organization** Apple Developer Program account, and who is the Account Holder?
- **Why it matters:** Required to publish on the App Store; organization verification can take significant time.
- **Owner:** Client  
- **Due:** Day 1–3 of kickoff  
- **Status:** Open  
- **Needed from client:** Enrollment confirmation + Admin/App Manager invite for delivery team  

### Q2. Google Play Console account

- **Question:** Which Google account / organization will own the Play listing, and can the delivery team receive Release Manager (or Admin) access?
- **Why it matters:** Required to publish on Google Play.
- **Owner:** Client  
- **Due:** Week 1  
- **Status:** Open  
- **Needed from client:** Console invite + confirmation developer identity verification is complete  

### Q3. Base44 access

- **Question:** Can delivery get admin (or sufficient) access to the Base44 project, including build/export settings, environments, and domains?
- **Why it matters:** Cannot audit packaging path or produce store binaries without it.
- **Owner:** Client  
- **Due:** ASAP  
- **Status:** Open  
- **Needed from client:** Invites + environment URLs + any existing mobile build documentation  

### Q4. Privacy Policy & Terms URLs

- **Question:** What are the final public HTTPS URLs for Privacy Policy and Terms of Use?
- **Why it matters:** Both stores expect a privacy policy; Apple will reject without adequate privacy disclosures.
- **Owner:** Client (legal)  
- **Due:** Week 1–2  
- **Status:** Open  
- **Needed from client:** Live links that match actual data practices  

### Q5. Support contact

- **Question:** What support email and/or support URL should appear on store listings, and who monitors it at launch?
- **Why it matters:** Store requirement and resident trust.
- **Owner:** Client ops  
- **Due:** Week 2  
- **Status:** Open  

### Q6. Final public app name

- **Question:** Is **Apex Connect** the final display name on both stores? Any legal entity suffix or DBA constraints?
- **Why it matters:** Affects icon text, listings, bundle identifiers, and trademarks.
- **Owner:** Client  
- **Due:** Week 2  
- **Status:** Open  

### Q7. Base44 mobile packaging capability

- **Question:** Does the current Base44 setup support generating store-compliant iOS and Android binaries (or an approved wrapper workflow)?
- **Why it matters:** If not, the technical plan must pivot immediately (Week 1–2 gate).
- **Owner:** Engineering (validate) + Client (access)  
- **Due:** Day 14 gate  
- **Status:** Open — validation blocked on Q3  

---

## P1 — Compliance, quality, and listing

### Q8. Account model & roles

- **Question:** What roles exist (tenant, property manager, complex admin, internal ops)? How is shared visibility granted and revoked?
- **Why it matters:** Security audit, review notes, and QA scripts.
- **Owner:** Client product + Engineering  
- **Status:** Open  

### Q9. Account deletion

- **Question:** How can a user delete their account (in-app, web form, or email request), and what is the SLA?
- **Why it matters:** Apple requires a deletion path when accounts can be created.
- **Owner:** Client + Engineering  
- **Status:** Open  

### Q10. Data collection inventory

- **Question:** Exactly what data is collected (name, email, phone, address, property IDs, photos, device IDs, analytics, location)?
- **Why it matters:** Apple App Privacy labels and Google Data safety must be accurate.
- **Owner:** Engineering (inventory) + Client (confirmation)  
- **Status:** Open  

### Q11. Third-party SDKs

- **Question:** Which analytics, crash reporting, chat, maps, or payment SDKs are embedded?
- **Why it matters:** Privacy forms and potential policy review.
- **Owner:** Engineering (via Base44 config)  
- **Status:** Open — blocked on access  

### Q12. Brand assets

- **Question:** Can the client provide final logo (SVG/PNG), preferred icon concept, brand colors, and any photography guidelines?
- **Why it matters:** Store creatives and icon approval.
- **Owner:** Client / brand  
- **Status:** Open  
- **Drop files in:** `assets/logos/`  

### Q13. Demo accounts for reviewers

- **Question:** Can we create stable demo users for each role that App Review / Play review can use without contacting real residents?
- **Why it matters:** Login-gated apps are commonly rejected without working demo credentials.
- **Owner:** Client ops + Engineering  
- **Status:** Open  

### Q14. Geographic scope messaging

- **Question:** Should store listings say service is available in GA/AL today, or use more general “U.S. properties” language while expansion is planned?
- **Why it matters:** Avoid misleading metadata; set resident expectations.
- **Owner:** Client marketing + delivery  
- **Status:** Open  

### Q15. Payments or paid features

- **Question:** Does the app include payments, subscriptions, or tips?
- **Why it matters:** Extra store configuration and possible IAP rules.
- **Owner:** Client  
- **Status:** Open  

### Q16. Push notifications

- **Question:** Are push notifications part of v1, and are they fully implemented end-to-end?
- **Why it matters:** Incomplete notification UX is a review and quality risk.
- **Owner:** Client + Engineering  
- **Status:** Open  

---

## P2 — Clarifications & post-launch

### Q17. Store category

- **Question:** Preferred primary category (e.g., Business vs Utilities vs Lifestyle)?
- **Owner:** Client  
- **Status:** Open  

### Q18. Rollout strategy

- **Question:** Prefer Google Play staged rollout (e.g., 20% → 100%) and Apple manual release after approval?
- **Owner:** Client  
- **Status:** Open  

### Q19. Analytics & success metrics

- **Question:** Which launch KPIs matter (installs, complaint submissions, time-to-route, crash-free sessions)?
- **Owner:** Client  
- **Status:** Open  

### Q20. Native rebuild timing

- **Question:** After store launch, is the preference to stabilize on Base44 for N months, or begin native rebuild immediately?
- **Owner:** Client + delivery  
- **Status:** Open  
- **Reference:** [`technical-plan.md`](technical-plan.md)  

### Q21. Nationwide expansion prerequisites

- **Question:** What must be true operationally before onboarding properties outside GA/AL (support staffing, SLAs, legal, routing rules)?
- **Owner:** Client ops  
- **Status:** Open  

---

## Required access checklist (client)

Use this as a shareable punch list:

- [ ] Apple Developer Program — Organization enrollment  
- [ ] App Store Connect — team invites  
- [ ] Google Play Console — team invites  
- [ ] Base44 — project admin / build access  
- [ ] Production & staging URLs  
- [ ] Test users for each role  
- [ ] Privacy Policy URL  
- [ ] Terms of Use URL  
- [ ] Support email / URL + monitoring owner  
- [ ] Logo / icon source files  
- [ ] Written approval process for store copy (who signs off?)  

---

## Required assets checklist (client)

- [ ] App icon master (1024 × 1024+)  
- [ ] Logo lockups (light / dark if applicable)  
- [ ] Brand color values  
- [ ] Optional: brand photography for store feature scenes (no PII)  
- [ ] Final short description  
- [ ] Final long description  
- [ ] “What’s New” blurb for 1.0  

Place deliverables in:

- `assets/logos/`  
- `assets/screenshots/` (after device capture)  
- `assets/app-store-assets/` (final packaged creatives)  

---

## Resolved

| ID | Question | Resolution | Date |
|----|----------|------------|------|
| — | — | None yet | — |

---

## How to update this file

1. Change **Status** to `Answered`, `Deferred`, or `Blocked`.  
2. Move answered items into **Resolved** with a one-line resolution.  
3. Reflect timeline impact in [`60-day-roadmap.md`](60-day-roadmap.md) if a P0 slips.  
4. Mention the change in the next status update / meeting notes.
