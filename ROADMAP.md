# Sheeba — MVP Launch Tracker

The single source of truth for where Sheeba stands.
Vision lives in the Master Blueprint. Interface rules live in the MVP Interface & Experience Architecture. **This file decides what is above the launch line.**

## Status legend

- ⬜ Not started
- 🔨 In progress
- 🟡 Built, awaiting test
- ⏸ On hold, waiting for something from Christopher
- ✅ Live and verified

**The rule:** nothing becomes ✅ until Claude has verified it live **and** Christopher has tested it himself.

Tags: `backend ready` means the server side already exists and is live, so only the interface is needed. `backend needed` means the server needs new work first.

## How work moves

1. Claude writes and tests the change.
2. The agent pushes it to the `staging` branch. Testing on staging is free.
3. Christopher tests on staging--maviolevel.netlify.app.
4. Tested changes are batched and released to `main` together (each release costs 15 Netlify credits).
5. Claude verifies the live release, then the item turns ✅ here.

---

## Phase 0 — Foundations

- ✅ Backend on Render, auto-deploys from GitHub
- ✅ Next.js + Tailwind frontend (maviolevel), auto-deploys from GitHub
- ✅ Staging branch with free test deploys, and a deployment rule for the agent
- ✅ Discover: real shops, search, categories, Near Me with real GPS distance
- ✅ Public shop pages at /shop/..., shareable links
- ✅ Privacy: Ghana Card details, legal names and passwords never exposed publicly
- 🟡 Ghana Card verification, Layer 1: stylist side tested; admin reject and approve not yet tested
- 🟡 Welcome pop-up after login and "Signed in as" label: live, not yet tested
- 🟡 Login accepts every normal way of writing a Ghana number (0544…, +233 54…, with spaces)
- 🟡 Navigation between Discover, My Shop and Admin, and Admin's own login page (on staging)
- 🟡 Security fixes: customer names, phone numbers and emergency contacts no longer public, no requests in someone else's name, no point farming, no booking theft, no fake ratings, crash protection (backend; name and phone privacy confirmed live by Christopher)
- 🟡 Shop data protection: every field checked, photos must be real uploads (no tracking images), per-photo and per-shop storage limits so no shop can lock itself out

## Phase 1 — Launch blockers

These stop the core journey from working. They come first.

- 🟡 Admin: approve new shops, so new professionals become visible to customers: card grid with a detail panel, bright admin theme (tested on staging by Christopher; goes live with the October 1 release)
- 🟡 Professional: accept, decline and complete requests from the dashboard, with call and WhatsApp buttons (tested on staging by Christopher)
- 🟡 Customer: send a request or booking from a shop page, with date and time (tested on staging by Christopher)

## Phase 2 — Interface foundation

- 🟡 Mobile-first layout: bottom tab bar on phones, top tabs on larger screens (on staging); tablet-landscape polish continues page by page
- 🔨 Design tokens: colours done (named by meaning, every text colour checked for readability in both themes); spacing, type sizes and radius still to do
- 🟡 Light, dark and Auto themes: readable in both, works on older phones, no white flash on load (tested on staging by Christopher)
- 🟡 Toast pop-ups (built and live, reusable)
- 🟡 Shared loading, error and empty states with a next step (on staging; used on Discover and My Requests, added to other lists as they're built)
- 🟡 App shell: one navigation on every page, role-aware (Admin tab only for admins), kept short (tested on staging by Christopher); now also shows customers Appointments, My Sheeba and Saved, and visitors a Sign in tab (built; held on hold/part1 until the combined release)

## Phase 3 — Discovery

- 🟡 Visual Discover: Live strip, rows (Near you, New looks, Loved on Sheeba, Popular this week, Professionals), masonry Explore feed, search Focus mode, context panel that opens in place (on staging)
- 🟡 Lean Discover feed: small photo versions and no private data, about 25x less mobile data than loading full shops (on staging)
- ⏸ Category drawings: ON HOLD. The first draft didn't represent the categories well; text categories stay until Christopher provides proper designs to build from
- 🟡 Work tiles (photo, service, price, heart) and professional cards (availability, price from, how they work) (on staging)
- 🔨 Public professional page: photos, work per service, How I work, a Book button at the top, visits counted (on staging); reviews and portfolio gallery still to do
- ⬜ Style library: named styles by category, with other names for search (`backend needed`)
- ⬜ Inspiration photos: licensed for commercial use, credited, clearly labelled "Inspiration", never shown as anyone's portfolio
- ⬜ Professionals tag their uploaded work with a style, so every style leads to people who actually do it (`backend needed`)
- 🔨 Trending from real engagement: "Loved on Sheeba" (hearts) and "Popular this week" (shop visits) are real and on staging; per-style trending waits for the style library
- 🟡 Live Mode basics: featured strip drifts gently, pauses on hover, touch or focus, stops in search, never moves with reduced-motion settings (on staging)

## Phase 4 — Customer workspace

- 🟡 Customer accounts: register and log in (built, not yet tested on the new site)
- 🟡 My Sheeba: what's coming up, what's due (reminders with pause/remove), saved styles with photos and notes, invite code, account settings (built; held on hold/part1 until the combined release)
- 🟡 Appointments (customer): Upcoming and Past, shop names, dates, prices in the right currency; Book again, Save this style, Remind me (built; held on hold/part1 until the combined release)
- 🟡 Saved shops, and a Save shop button on every shop page (built; held on hold/part1 until the combined release)
- 🟡 Customer privacy and safety fixes: Saved shops no longer sends shop owners' ID documents, legal names or phone numbers; nobody can follow as someone else; Save This Style photos must be real uploads; Book again has the same checks as booking; Remind Me intervals 1 week to 1 year (built; held on hold/part1 until the combined release)
- ⬜ Messages, split view on larger screens (`backend ready`)
- ⬜ **Next update:** customer QR: a logged-in professional scans it to check the customer in, link the visit to their history and add them as a customer, and the customer confirms on their own phone; anyone else who scans sees nothing personal (`backend needed`)

## Phase 5 — Professional workspace

- 🔨 Home: today, pending requests, next actions (basic version live)
- 🔨 Real appointment dates and times: stored with every new request; "who's coming today" view still to build
- ⬜ Calendar: day view first (needs the item above)
- 🟡 Services: add, edit, hide, delete, with price, duration, description and a work photo (on staging)
- 🟡 Shop and profile editing: profile and cover photos, description, category, area, availability, GPS location, completeness checklist (on staging)
- 🟡 How I work: salon, home, mobile, by appointment (on staging)
- ⬜ Customers: list plus detail, private notes, history, due soon (`backend ready`)
- ⬜ Messages (`backend ready`)
- ⬜ Earnings statement: recorded service value, not payments (`backend ready`)
- 🟡 Sheeba code for every account (e.g. K7M 2QX): permanent for life across roles, random, never guessable; short link /u/CODE; QR to show, download, print for the salon and share on WhatsApp; older accounts get theirs automatically (built; held on branch hold/part1 until the combined release)
- 🟡 Invite rewards: GH₵1 when someone joins with your code and completes their first job; shown under Share & earn (professionals) and My Requests (customers); admin reviews each qualifying job, pays by hand and records the reference; flag when the inviter was on the job (built; held on branch hold/part1 until the combined release)
- ⬜ Apprentice and staff access: the MVP version of the trainee system (`backend ready`)
- 🟡 Change password, for professionals and customers (on staging)

## Phase 6 — Admin control center

- 🔨 Separate admin environment (basic version live)
- 🟡 ID verification queue (built, not yet tested)
- 🟡 Shop review queue (see Phase 1)
- ⬜ Reports and account restrictions (`backend ready`)
- 🟡 Password recovery: "Forgot password?" for everyone, admin help queue confirmed by calling the number on the account, temporary password that must be changed (on staging)
- ⬜ Limit repeated wrong-password attempts, to stop password guessing (`backend needed`)
- ⬜ Public shop data still lists follower and like ID codes: show counts instead, keeping follow buttons working (low risk)
- ⬜ Professionals and users: search, table, detail panel (`backend ready`)
- ✅ Audit log of admin actions

## Phase 7 — Launch readiness

Not all of this is code.

- ⬜ Collect style names and licensed inspiration photos, with credits (Christopher; spreadsheet)
- ⬜ Recruit the first real professionals, and encourage them to upload and tag their own work
- ⬜ End-to-end journey tests: customer, professional, admin
- ⬜ Device checks: phone, tablet landscape, desktop
- ⬜ Ask NIA whether regulation L.I. 2523 applies to Sheeba's ID checks
- 🟡 Works outside Ghana (Ghana and the UK to start; adding a country = one entry): country at signup sets the shop's currency; phone logins in any local or international format; miles in the UK; ID documents per country (UK: passport, driving licence or residence permit; duplicates caught across document types); Discover shows your own country's shops with local budgets; WhatsApp links per country (built; held on hold/part1 until the combined release)
- 🟡 Phone numbers stored in one tidy form, so a number saved with spaces can be found from any format (checked: no existing account needed fixing)
- ⬜ Clear all test data before launch: test shops, test ID submissions, and any photo not taken by the professional themselves
- ⬜ Sheeba Help: one help guide written from the real app, with an assistant that answers only from it; a Help chat inside Sheeba (reaches everyone) and the existing Telegram bot connected to the same brain; anything account-specific handed to the admin as a ticket; never asks for passwords or ID numbers; WhatsApp later (Meta approval and fees); Discord skipped
- ⬜ Point sheeba.online to the new site
- ⬜ Retire the old versions once the switch is confirmed

---

## ═══════ MVP LAUNCH LINE ═══════

Everything above must be ✅ before inviting the public. Everything below comes after launch.

---

## Post-launch (planned)

- Separate Professional from Shop, so identity follows the professional (Blueprint Decision 1)
- Full trainee workspace: training progress, supervisor relationship, career path (needs the item above)
- Team workspace
- Live Mode, advanced: ambient displays for shop tablets, idle detection, more rotating areas
- Glow Points: customer loyalty (a new system, separate from professional points)
- Turn professional points into quiet ranking signals instead of public badges
- Budget-to-service search ("what can I get for my budget?")
- Ghana Card Layer 2: automatic NIA lookup and selfie match (needs a provider and fees)
- Phone number verification by SMS
- Payments: switch on Paystack
- Community feedback from Telegram in Admin
- Admin analytics
- Move photos to cloud storage with automatic small versions (keeps data costs low as Sheeba grows past a few hundred shops)

## Future

- AI recommendations, native mobile apps, multiple countries and currencies, market intelligence, digital professional passport

---

## Decisions log

- **Brand pink for buttons:** #e31f64 instead of #e63875 (same hue, 5.5% deeper) so white button text is readable (4.52:1). Christopher may revert.
- **Launch line position:** agreed by Christopher.
- **Device priority:** mobile first, then tablet landscape, then desktop. Confirmed: a phone-friendly web app now, Play Store app later.
- **Discovery content:** style names can be collected freely. Photos only from sources that allow commercial use, credited and labelled as inspiration, never presented as a professional's work. Trending is based on real engagement on Sheeba.
- **Points naming:** existing points are professional growth points. Glow Points is a separate, future customer loyalty system. This corrects the rename to-do in Blueprint v3.
- **Trainee system:** decided (Option A). Apprentice and staff access is the MVP version; the full trainee workspace comes after launch, following the Professional/Shop split.
- **Netlify credits:** no releases to `main` until October 1 unless something is broken.
- **Invite rewards:** GH₵1 per invited person's first completed job, paid by hand by Christopher from his own funds after reviewing each one in Admin. Rewards are recorded in cedis for every country until another currency's amount is set.
- **International from the start:** Sheeba must work for people outside Ghana (first case: the UK). Location decides currency, formats and ID documents.
