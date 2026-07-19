# Current App Audit — Apex Connect (Base44)

**Purpose:** Establish what exists today, what is store-ready, and what must be fixed or deferred before Apple App Store and Google Play submission.  
**Platform:** Base44  
**Audit status:** In progress — access-dependent sections marked **BLOCKED**  
**Last updated:** July 2026

---

## 1. Executive summary

Apex Connect is a Base44-built application for a waste management company serving multi-unit residential properties. The product’s core differentiator is **shared account visibility** between tenants and apartment complexes so that **complaints and service issues route to the correct property / location**.

The company currently operates in **Georgia and Alabama** and intends to expand nationwide. The 60-day objective is **store launch of the current product path**, not a ground-up native rewrite.

This audit is the baseline for packaging, QA, and store policy readiness. Several items remain blocked until Base44 and store account access are granted (see Section 8).

---

## 2. Product understanding (as of discovery)

### Intended users

| Persona | Likely needs |
|---------|----------------|
| Tenant / resident | Report issues, see status, understand their property context |
| Property / apartment complex staff | Shared visibility into complaints for their locations |
| Internal company ops (if in-app) | Route and resolve service issues by property |

### Core value to preserve for v1 store release

1. Reliable authentication  
2. Correct property / location association  
3. Complaint (or equivalent service request) submission  
4. Visibility rules that match the client’s routing model  
5. Professional, trustworthy presentation suitable for public stores  

### Markets

- **Live / primary:** Georgia, Alabama  
- **Planned:** Nationwide expansion (post-stabilization; not a blocker for first store listing if the app functions for current properties)

---

## 3. Platform & architecture snapshot

| Item | Finding | Confidence |
|------|---------|------------|
| Builder | Base44 | High |
| Native code ownership | Not in this repo; `src/` is a placeholder | High |
| Backend / data | Assumed managed via Base44 services — **needs verification** | Low |
| Auth | Present (details TBD) | Medium |
| Push notifications | Unknown | — |
| File / photo uploads | Likely for complaints — **needs verification** | Low |
| Offline support | Unknown; assume online-required for v1 | Low |
| Custom domain | Unknown | — |

**Engineering note:** Treat Base44 as the system of record until an export or rebuild lands. Do not invent parallel production code in this repository.

---

## 4. Feature inventory

Statuses: `Confirmed` · `Assumed` · `Unknown` · `Missing` · `Out of scope for v1`

| Feature area | Status | Store impact | Notes |
|--------------|--------|--------------|-------|
| User registration / login | Assumed | Critical | Need exact methods (email, magic link, SSO) |
| Password reset | Unknown | High | Required if password auth exists |
| Tenant ↔ property association | Confirmed (concept) | Critical | Validate edge cases in QA |
| Apartment complex shared visibility | Confirmed (concept) | Critical | Document rules for App Review notes |
| Complaint / issue submission | Confirmed (concept) | Critical | Confirm fields, attachments, SLAs |
| Complaint status / history | Assumed | High | Listing should not promise what UI lacks |
| Multi-location switching | Unknown | Medium | Important for complexes with multiple sites |
| Admin / ops console in mobile app | Unknown | Medium | May be web-only — clarify for listing copy |
| Payments / billing | Unknown | High if present | Triggers extra store & policy work |
| Maps / geolocation | Unknown | Medium | Declare in privacy forms if used |
| Push notifications | Unknown | Medium | Only ship if fully implemented |
| In-app support / chat | Unknown | Low | Support URL may suffice for v1 |
| Nationwide property onboarding | Out of scope for v1 | — | Roadmap after launch |

---

## 5. UX & brand readiness

| Area | Assessment | Action |
|------|------------|--------|
| Visual polish | Not yet audited on device builds | Capture screenshots from RC build only |
| App name consistency | “Apex Connect” used in this repo; confirm legal/display name | Client confirmation required |
| Iconography | Assets folder empty — awaiting brand files | Collect into `assets/logos/` |
| Empty / error states | Unknown | Include in QA script |
| Accessibility baseline | Unknown | Spot-check Dynamic Type / large fonts if time |
| Mobile web vs installed app parity | Unknown | Confirm Base44 mobile packaging behavior |

---

## 6. Security, privacy & trust

| Check | Status | Notes |
|-------|--------|-------|
| HTTPS everywhere | Assumed | Verify in production build |
| Role-based data isolation | Critical — needs proof | Tenants must not see other properties’ data |
| PII handling documented | Missing | Needed for Privacy Policy + store forms |
| Account deletion | Unknown | Apple requires a path if accounts are created |
| Session timeout / logout | Unknown | Include in QA |
| Secrets in client | Unknown | Audit Base44 config once access granted |
| Admin impersonation / shared logins | Risk if used | Discourage shared passwords; prefer proper roles |

**Store risk flag:** Shared visibility across tenants and complexes is a product feature—not a bug—but must be explained carefully in review notes and privacy copy so reviewers understand intentional multi-party access.

---

## 7. App Store readiness gap analysis

| Store requirement | Ready? | Gap |
|-------------------|--------|-----|
| Apple Developer org account | No | Client enrollment / invite pending |
| Google Play Console | No | Client enrollment / invite pending |
| Privacy Policy URL | No | Client legal |
| Terms of Use URL | No | Client legal |
| Support contact | No | Client ops |
| App icon & screenshots | No | Brand + QA builds |
| Store descriptions | Draftable | Needs client approval |
| iOS binary | No | Base44 packaging + signing |
| Android AAB | No | Base44 packaging + signing |
| Privacy nutrition labels / Data safety | No | Requires data inventory |
| Demo reviewer account | No | Create after auth model confirmed |

Detailed execution list: [`app-store-launch-checklist.md`](app-store-launch-checklist.md)

---

## 8. Access required to finish this audit

**BLOCKED** until received:

1. Base44 project invite (admin or equivalent)  
2. Staging / production URLs and test users for each role (tenant, property staff, ops if applicable)  
3. Confirmation of auth methods and account lifecycle  
4. Confirmation of whether the mobile experience is Base44’s native wrapper, PWA, or another packaging path  
5. List of third-party SDKs / analytics / chat tools embedded in the app  
6. Geographic restrictions (hard-coded GA/AL vs data-driven property list)

---

## 9. Preliminary risk findings

| Risk | Severity | Why it matters | Recommended next step |
|------|----------|----------------|------------------------|
| Unverified packaging path from Base44 to both stores | High | Blocks binary production | Validate in Week 1 (`technical-plan.md`) |
| Unclear data-visibility rules | High | Privacy + trust + review rejection | Document matrix with client |
| Missing legal URLs | High | Submission blocker | Client provides live links |
| Apple org verification delay | High | Can consume weeks | Start enrollment Day 1 |
| Listing overclaims vs actual features | Medium | Rejection / user distrust | Align copy to audited UI |
| Nationwide messaging vs GA/AL reality | Low–Medium | Misleading metadata risk | Phrase growth as roadmap, not current coverage |

---

## 10. Recommended audit next steps (ordered)

1. Obtain Base44 + test account access  
2. Record end-to-end demos for each persona  
3. Fill the feature inventory statuses (`Unknown` → `Confirmed` / `Missing`)  
4. Produce a **data collection inventory** for privacy forms  
5. Decide v1 feature freeze (what reviewers will see)  
6. Run a store-policy preflight against unfinished screens  
7. Update this document’s confidence levels and clear the BLOCKED sections  

---

## 11. Sign-off

| Role | Name | Date | Sign-off |
|------|------|------|----------|
| Delivery lead | TBD | | Audit complete for packaging |
| Engineering | TBD | | Technical findings accurate |
| Client product owner | TBD | | Feature freeze accepted |

This audit should be re-reviewed at the Phase 1 gate (Day 14) and again before first store submission.
