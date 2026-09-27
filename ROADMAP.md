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

## Feedback round 1 (from Christopher's full test) — next build

Build order: Round 1 = A, E, G, F (built); Round 2 = D; Round 3 = B, C, H1; later H2 (video). One combined push after Round 3.

- 🟡 A. Accidental pull-down refresh wiped half-filled forms: switch off pull-to-refresh app-wide and keep half-filled forms through reloads (never passwords) (built; held on hold/feedback1)
- 🟡 A. Location control becomes a small on/off icon, like a phone's location toggle (built; held on hold/feedback1)
- 🟡 A. Countries shown as flag + code (🇬🇭 GH, 🇬🇧 UK) (built; held on hold/feedback1)
- 🟡 E. Every country at signup (searchable, flag + name); Ghana and UK keep full setup; other countries get their currency, international phone numbers, and passport / national ID / driving licence verification; uses a maintained open-source country list (built; held on hold/feedback1)
- ⬜ B. Feed follows the user's location automatically; a small "📍 City · GH" label opens change-location / compare instead of big country buttons
- ⬜ B. "Any budget" replaced by real local price ranges from what professionals in the area charge, per category ("Up to GH₵120 · typical near you")
- ⬜ B. Compare prices across cities and countries (within a country exact; across countries each local price plus a clearly marked approximate conversion)
- ⬜ B. For stylists: "what others nearby charge" beside their prices
- ⬜ B. Shops choose a city (area stays as the neighbourhood); a place's price range shows only once 3+ professionals there have prices
- 🟡 Age policy (admin switch, off by default): 18+ for customers and professionals via one checkbox; apprentices from 15 (Children's Act, 1998, s.98) with a parent or guardian's name, phone and consent; under-18 apprentices never public, no direct bookings; stated in the Terms (built; held on hold/feedback1)
- 🟡 Stricter invite checks: a referral counts only when the invited person completes a genuine first job; checked for 7 days then confirmed automatically; warning signs (inviter on the job, first job within 24 hours of joining, repeated referrals completing with the same professional) go to admin review; no cash payouts (built; held on hold/feedback1)
- ⬜ D. Two-level services: Services (Hair styling, Barbering, Makeup, Nails, Lashes & brows, Skin & spa…) each with their own styles; Barbering is a service, not a style
- ⬜ D. Professionals can add an activity that isn't listed: shows on their shop at once, goes to admin review, becomes available to everyone once approved
- ⬜ C. Optional customer onboarding after signup: "Show me styles for" (men's grooming / women's / both / prefer not to say) and "Pick your 3 favourites"; feed ranking uses it (men see barbering first unless their favourites include braids, locs, etc.); editable in My Sheeba; never shown to professionals
- 🟡 F. Invite rewards become future coupons: no cash while Sheeba takes no payments; rewards build up (shown in money terms) and become coupon codes for a free or discounted service once Sheeba is monetised; admin "mark as paid" becomes a ledger. BUG: UK accounts show "GH₵1". DECIDED: every invite is worth the equivalent of GH₵1 at the real exchange rate; rewards recorded in cedis (one clean liability figure), shown as the local equivalent at today's rate (e.g. GH₵1 ≈ £0.07), converted at that day's rate when coupons are issued; daily rates from an exchange-rate source (shared with the cross-country price comparison) (built; held on hold/feedback1)
- 🟡 F. Founding members: every account gets a signup number (existing accounts numbered by join date); members #1–1,000 are founding members; the 1,000th signup is celebrated as a milestone; friendly name-based code (e.g. AKUA0042) for sharing and invites, while the QR carries a hidden secret for check-in (friendly codes are guessable) (built; held on hold/feedback1)
- 🟡 F. Terms and Privacy pages (needed before launch anyway), including an optional clause: professionals may choose to reward customers who refer others (built; held on hold/feedback1)
- 🟡 G. Customers never see My Shop: customer tabs are Discover, Appointments, My Sheeba, Saved; professionals enter through a separate "For professionals" entrance (built; held on hold/feedback1)
- 🟡 G. Share button opens the phone's own share menu (WhatsApp, Instagram, TikTok, Facebook, SMS…), with buttons as a fallback on computers (built; held on hold/feedback1)
- 🟡 G. Invite page adds "I'm training (apprentice)": short signup asking for the supervisor's code; the shop owner approves the link (built; held on hold/feedback1)
- 🟡 G. Phone numbers the international way: flag + dial-code picker (🇬🇧 +44) on every signup and login; starts on the inviter's country (built; held on hold/feedback1)
- 🟡 G. The invite code at signup explained: "Invited by Grace's Studio", with a way to change it (built; held on hold/feedback1)
- 🟡 G. Customer self check-in: a customer with an appointment today scans the shop's QR on arrival and gets "I'm here: check in" (built; held on hold/feedback1)
- ⬜ H. A feed that learns from behaviour (what people view, linger on, heart, save, search and book), plus voice search the user chooses to use (tap the mic, say what you want). No secret listening: illegal under Ghana and UK data law, blocked by browsers, and it would destroy trust
- ⬜ H. Video feed of professionals' work (scrolling, like Reels): needs cloud storage with automatic compression first, and data-saving playback (no autoplay on mobile data unless chosen)
- ⬜ D. Load Christopher's style spreadsheet (received: 15 rows, Pexels, credited) into the style library: 11 distinct styles, with the 4 general braiding photos merged in as extra photos; shown only as "Inspiration"
- ⏸ Christopher to gather more styles in the same format: men's barbering (fades, low cut, waves, beard, shape-ups), makeup, nails, lashes

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
- 🟡 PRIVACY HOTFIX, LIVE: "shops I follow" no longer sends shop owners' ID numbers, ID photos or legal names (deployed and verified by Claude; every other list route on the live server checked and found properly protected)
- 🟡 Customer privacy and safety fixes: Saved shops no longer sends shop owners' ID documents, legal names or phone numbers; nobody can follow as someone else; Save This Style photos must be real uploads; Book again has the same checks as booking; Remind Me intervals 1 week to 1 year (built; held on hold/part1 until the combined release)
- ⬜ Messages, split view on larger screens (`backend ready`)
- 🟡 Customer QR check-in: a professional scans or types the customer's code and checks them in; the customer's name is shown ONLY if they already have an appointment together; the customer is notified and both see the check-in time; showing the code is the customer's consent (built; held on hold/part1 until the combined release)

## Phase 5 — Professional workspace

- 🔨 Home: today, pending requests, next actions (basic version live)
- 🟡 Real appointment dates: a Today view (who's coming, in time order, opens by default when someone's booked) and Upcoming grouped by day (built; held on hold/part1 until the combined release)
- 🟡 Calendar, day view: Today plus a by-day Upcoming list (built; held on hold/part1 until the combined release); a full week calendar comes later
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
- ⬜ URGENT: ask NIA whether regulation L.I. 2523 applies to Sheeba's ID checks (its transition period ends 2 November 2026)
- ⬜ Automated verification (Layer 2): a provider connected to NIA's records checks the card and matches a live selfie; clear matches approved automatically, clear failures rejected automatically, only borderline cases go to the admin. Build the automatic pipeline with a provider plug-in slot now; switch on when Christopher has a provider account (per-check fees; ideally one provider covering Ghana Cards and UK documents). Also needs: Sheeba registered as a business, and registration with Ghana's Data Protection Commission
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
- Phone number verification by SMS
- Payments (decision pending, Claude's recommendation: not at launch): payments happen directly between customer and stylist (cash or MoMo) at first; the likely first use later is an OPTIONAL deposit against no-shows, via Paystack split payments straight to the stylist's Mobile Money, with Sheeba taking 0% (only Paystack's own fee). The secure Paystack module already exists on the backend, unused
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
- **Invite rewards (updated):** no cash payouts while Sheeba takes no payments. Rewards (the equivalent of GH₵1 per invited person's first completed job, in every country, at the real exchange rate) build up in each account and become coupon codes for a free or discounted service once Sheeba is monetised.
- **International from the start:** Sheeba must work for people outside Ghana (first case: the UK). Location decides currency, formats and ID documents.
