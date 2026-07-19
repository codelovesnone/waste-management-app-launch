# App Store Launch Checklist

**Product:** Apex Connect  
**Stores:** Apple App Store · Google Play  
**Use:** Work through every section before first submission. Check items only when verified.

---

## 0. Accounts & access

### Apple

- [ ] Apple Developer Program membership active (**Organization** preferred)
- [ ] App Store Connect access for delivery team (Admin or App Manager)
- [ ] Agreements, tax, and banking completed in App Store Connect
- [ ] Distribution certificate / cloud signing path confirmed
- [ ] App record created in App Store Connect
- [ ] Bundle ID reserved and matches build

### Google

- [ ] Google Play Console account created (organization / developer identity verified)
- [ ] Play Console invites for delivery team (Admin or Release Manager)
- [ ] Play Console payments profile / developer identity complete as required
- [ ] App created in Play Console
- [ ] Application ID (package name) reserved and matches build

### Product / platform

- [ ] Base44 project admin access granted
- [ ] Ability to generate iOS and Android store builds confirmed
- [ ] Production API / backend URLs confirmed for store builds
- [ ] Demo / reviewer login credentials created and documented

---

## 1. Legal, privacy & compliance

- [ ] Privacy Policy URL live (HTTPS) and linked in both store listings
- [ ] Terms of Use URL live (recommended; required if account creation exists)
- [ ] Support email or support URL monitored
- [ ] Data collection inventory completed (account, location, device, photos, etc.)
- [ ] Apple App Privacy “nutrition labels” completed accurately
- [ ] Google Play Data safety form completed accurately
- [ ] Account deletion pathway documented (Apple requirement if accounts are created)
- [ ] Content rating / age rating questionnaires completed
- [ ] No hidden or undocumented tracking SDKs in the store build

---

## 2. App identity & branding

- [ ] Final public app name approved by client
- [ ] Subtitle / short description approved (Apple subtitle ≤ 30 characters)
- [ ] App icon finalized (no excessive transparency / misleading imagery)
- [ ] Splash / launch screen acceptable on iOS and Android
- [ ] Brand colors and logo usage consistent with company identity
- [ ] Source logo files stored in `assets/logos/`
- [ ] Final store creatives stored in `assets/app-store-assets/`

---

## 3. Store listing content

### Shared copy

- [ ] Short description (Play) approved
- [ ] Full description approved — clear value for tenants / properties / waste ops
- [ ] Keywords researched (Apple) without competitor trademark stuffing
- [ ] Category selected (e.g. Utilities / Business — confirm with client)
- [ ] Contact email and marketing URL (if any) set
- [ ] What’s New text prepared for first release

### Screenshots & media

- [ ] iPhone screenshots for required display sizes
- [ ] Android phone screenshots (and tablet if tablet-supported)
- [ ] Feature graphic for Google Play (1024 × 500)
- [ ] Optional: App Preview video (only if high quality and approved)
- [ ] Screenshots show real product UI (no misleading mock functionality)
- [ ] No confidential property or personal data visible in screenshots
- [ ] Exports stored under `assets/screenshots/`

---

## 4. Technical readiness (Base44 → stores)

- [ ] Production build configuration documented (`technical-plan.md`)
- [ ] iOS build uploaded to App Store Connect (valid signing)
- [ ] Android App Bundle (AAB) uploaded to Play Console
- [ ] Version code / build number strategy agreed
- [ ] Deep links / custom URL schemes tested if used
- [ ] Push notifications configured only if fully implemented (do not advertise unfinished features)
- [ ] Offline / error states do not present a blank or broken shell app
- [ ] Minimum OS versions documented and acceptable to client

---

## 5. Functional QA (launch-critical)

Run on real devices where possible (one recent iPhone, one recent Android).

### Authentication & accounts

- [ ] Sign up / sign in works on both platforms
- [ ] Password reset (if offered) works
- [ ] Session persistence behaves correctly after app restart
- [ ] Sign out clears sensitive local state

### Property / location visibility

- [ ] Tenant can see the correct property context
- [ ] Apartment complex / property staff see shared visibility as designed
- [ ] Users cannot access properties they should not see
- [ ] Switching location / property (if applicable) is reliable

### Complaints & routing

- [ ] Complaint / service request can be submitted
- [ ] Submission routes to the correct property / location
- [ ] Status / history visible to intended roles
- [ ] Attachments (photos) work if featured in the listing

### Stability & polish

- [ ] No crash on cold start
- [ ] No blocking loading states without timeout/error
- [ ] Forms validate required fields
- [ ] External links open correctly
- [ ] Orientation / small-screen layouts usable

---

## 6. App Review preparation (Apple)

- [ ] Review notes explain the waste-management + multi-property model clearly
- [ ] Demo account username/password provided in App Store Connect
- [ ] Any paid features or gated regions explained
- [ ] If limited to GA/AL properties, explain geographic scope to reviewers
- [ ] Export compliance / encryption answers completed
- [ ] Advertising Identifier usage declared only if used
- [ ] App does not reference incomplete features in UI or listing

---

## 7. Play Console preparation (Google)

- [ ] Content rating questionnaire completed
- [ ] Target audience and content declared correctly
- [ ] News / COVID / other declarations answered accurately
- [ ] Data safety form matches actual SDK and data practices
- [ ] App access instructions provided if login required
- [ ] Countries/regions selected (start with US; expand later as needed)
- [ ] Production track or staged rollout percentage chosen with client

---

## 8. Pre-submission gate

Do not submit until all of the following are true:

- [ ] Privacy Policy URL opens correctly on mobile Safari and Chrome
- [ ] Demo account tested on the exact build under review
- [ ] Client written approval on listing name, icon, and screenshots
- [ ] Checklist sections 0–7 have no unchecked P0 items
- [ ] Rollback / hotfix owner named for launch week

---

## 9. Submission

### Google Play

- [ ] AAB uploaded to desired track
- [ ] Store listing attached
- [ ] Data safety + ratings complete
- [ ] Submitted for review
- [ ] Review status monitored daily

### Apple App Store

- [ ] Build selected for the version
- [ ] Screenshots + metadata complete for primary locale (EN-US)
- [ ] App Privacy complete
- [ ] Submitted for review
- [ ] Resolution Center monitored (respond within 24–48 hours)

---

## 10. Launch day & week-one ops

- [ ] Release manually or automatically per client preference
- [ ] Public store URLs captured and shared with client
- [ ] Install verification from a clean device (not previously provisioned)
- [ ] Crash reports / Base44 error monitoring watched for 7 days
- [ ] Support inbox triage process confirmed
- [ ] Known issues list published internally
- [ ] First update candidate scheduled if needed

---

## Quick reference — common rejection causes

| Cause | Prevention |
|-------|------------|
| Broken login / no demo account | Provide and retest reviewer credentials |
| Incomplete app / placeholder screens | Hide or remove unfinished features before submit |
| Privacy Policy missing or generic mismatch | Host accurate policy; match App Privacy answers |
| Misleading screenshots | Capture from production build only |
| Account deletion not offered | Provide in-app or web deletion flow + instructions |
| Crash on launch | Device QA on release candidate |

---

## Checklist ownership

| Section | Primary owner |
|---------|----------------|
| Accounts & access | Client + delivery lead |
| Legal & privacy | Client (legal) + delivery |
| Branding & listing | Client + design |
| Technical builds | Engineering |
| QA | Engineering + delivery |
| Submission | Engineering + delivery lead |
| Launch ops | Delivery lead + client ops |

Update this checklist as items clear. Prefer dated notes in [`client-meeting-notes.md`](client-meeting-notes.md) when an item is blocked.
