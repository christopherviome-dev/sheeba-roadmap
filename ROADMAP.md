# Mepluge (formerly Sheeba) — MVP Launch Tracker

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

- 🟡 A. Accidental pull-down refresh wiped half-filled forms: switch off pull-to-refresh app-wide and keep half-filled forms through reloads (never passwords) (on staging)
- 🟡 A. Location control becomes a small on/off icon, like a phone's location toggle (on staging)
- 🟡 A. Countries shown as flag + code (🇬🇭 GH, 🇬🇧 UK) (on staging)
- 🟡 E. Every country at signup (searchable, flag + name); Ghana and UK keep full setup; other countries get their currency, international phone numbers, and passport / national ID / driving licence verification; uses a maintained open-source country list (on staging)
- 🟡 B. Feed follows the user's location automatically; a small "📍 City · GH" label opens change-location / compare instead of big country buttons (on staging)
- 🟡 B. "Any budget" replaced by real local price ranges from what professionals in the area charge, per category ("Up to GH₵120 · typical near you") (on staging)
- 🟡 B. Compare prices across cities and countries (within a country exact; across countries each local price plus a clearly marked approximate conversion) (on staging)
- 🟡 B. For stylists: "what others nearby charge" beside their prices (on staging)
- 🟡 B. Shops choose a city (area stays as the neighbourhood); a place's price range shows only once 3+ professionals there have prices (on staging)
- 🟡 Age policy (admin switch, off by default): 18+ for customers and professionals via one checkbox; apprentices from 15 (Children's Act, 1998, s.98) with a parent or guardian's name, phone and consent; under-18 apprentices never public, no direct bookings; stated in the Terms (on staging)
- 🟡 Stricter invite checks: a referral counts only when the invited person completes a genuine first job; checked for 7 days then confirmed automatically; warning signs (inviter on the job, first job within 24 hours of joining, repeated referrals completing with the same professional) go to admin review; no cash payouts (on staging)
- 🟡 D. Two-level services: Services (Hair styling, Barbering, Makeup, Nails, Lashes & brows, Skin & spa…) each with their own styles; Barbering is a service, not a style (on staging)
- 🟡 D. Professionals can add an activity that isn't listed: shows on their shop at once, goes to admin review, becomes available to everyone once approved (on staging)
- 🟡 C. Optional customer onboarding after signup: "Show me styles for" (men's grooming / women's / both / prefer not to say) and "Pick your 3 favourites"; feed ranking uses it (men see barbering first unless their favourites include braids, locs, etc.); editable in My Sheeba; never shown to professionals (on staging)
- 🟡 F. Invite rewards become future coupons: no cash while Sheeba takes no payments; rewards build up (shown in money terms) and become coupon codes for a free or discounted service once Sheeba is monetised; admin "mark as paid" becomes a ledger. BUG: UK accounts show "GH₵1". DECIDED: every invite is worth the equivalent of GH₵1 at the real exchange rate; rewards recorded in cedis (one clean liability figure), shown as the local equivalent at today's rate (e.g. GH₵1 ≈ £0.07), converted at that day's rate when coupons are issued; daily rates from an exchange-rate source (shared with the cross-country price comparison) (on staging)
- 🟡 F. Founding members: every account gets a signup number (existing accounts numbered by join date); members #1–1,000 are founding members; the 1,000th signup is celebrated as a milestone; friendly name-based code (e.g. AKUA0042) for sharing and invites, while the QR carries a hidden secret for check-in (friendly codes are guessable) (on staging)
- 🟡 F. Terms and Privacy pages (needed before launch anyway), including an optional clause: professionals may choose to reward customers who refer others (on staging)
- 🟡 G. Customers never see My Shop: customer tabs are Discover, Appointments, My Sheeba, Saved; professionals enter through a separate "For professionals" entrance (on staging)
- 🟡 G. Share button opens the phone's own share menu (WhatsApp, Instagram, TikTok, Facebook, SMS…), with buttons as a fallback on computers (on staging)
- 🟡 G. Invite page adds "I'm training (apprentice)": short signup asking for the supervisor's code; the shop owner approves the link (on staging)
- 🟡 G. Phone numbers the international way: flag + dial-code picker (🇬🇧 +44) on every signup and login; starts on the inviter's country (on staging)
- 🟡 G. The invite code at signup explained: "Invited by Grace's Studio", with a way to change it (on staging)
- 🟡 G. Customer self check-in: a customer with an appointment today scans the shop's QR on arrival and gets "I'm here: check in" (on staging)
- 🟡 H. A feed that learns from behaviour (what people view, linger on, heart, save, search and book), plus voice search the user chooses to use (tap the mic, say what you want). No secret listening: illegal under Ghana and UK data law, blocked by browsers, and it would destroy trust (on staging)
- ⬜ H. Video feed of professionals' work (scrolling, like Reels): needs cloud storage with automatic compression first, and data-saving playback (no autoplay on mobile data unless chosen)
- 🟡 D. Load Christopher's style spreadsheet (received: 15 rows, Pexels, credited) into the style library: 11 distinct styles, with the 4 general braiding photos merged in as extra photos; shown only as "Inspiration" (on staging)
- ⏸ Christopher to gather more styles in the same format: men's barbering (fades, low cut, waves, beard, shape-ups), makeup, nails, lashes

## Feedback round 2 (27 Sep) — Discover redesign and Settings

- 🟡 Discover is one Instagram-style vertical feed: posts show the professional, their work large, love (double-tap too), share and Book; inspiration posts woven in; more posts load as you scroll (on staging)
- 🟡 Services roll across the top automatically (pause on touch; still for reduced-motion users); the chosen service is pinned (on staging)
- 🟡 Tapping inspiration opens a detail view: photos, other names, typical price nearby, and who does it near you; tapping Discover again or pressing Back returns to the feed (on staging)
- 🟡 Discover icon is a compass; top bar is just the location pin and Settings; country moved to Settings (set automatically at signup) (on staging)
- 🟡 Settings for every user: account, appearance (light/dark), country, location, feed preferences, clear what's been learned, password, community, terms and privacy, log out (on staging)
- 🟡 Footer: Terms · Privacy · Settings, plus Telegram and WhatsApp community logos (official logo files from each brand's own resources) (on staging)
- 🟡 WhatsApp community link added (footer and Settings) (on staging)
- 🟡 My Sheeba tidied: log out, password and feed preferences now live only in Settings (on staging)
- 🟡 My Shop reorganised like X: a clean Home (needs your answer, today, unread messages, apprentice work, this week, next step), and everything else in a menu behind the profile picture (drawer on phones, sidebar on larger screens), with count badges; nothing removed (on staging)
- 🟡 Profiles: professionals get a Profile page (photo, Verified and Founding badges, loves, jobs completed, customers served, work posted, services, saves, joined date); customers get a profile card with photo, badge and numbers at the top of My Sheeba (on staging)
- 🟡 Social proof on public shop pages: "♥ 124 loves · 38 jobs done on Sheeba" (on staging)
- 🟡 Bottom bar: visitors Discover · Search · Sign in; customers Discover · Search · Bookings · Inbox · Profile; professionals Discover · Search · My Shop (+ Admin) (on staging)
- 🟡 Search is its own screen: type or speak, local-price budgets, services, inspiration styles; results as Looks, Professionals and Styles (on staging)
- 🟡 Posts are Sheeba's own "look cards" (Christopher rejected the TikTok style: Sheeba must be distinct): photo inside a rounded card, ♥ with count in its corner, style name, price and duration, 📍 place and distance, the professional with Available/Away and Follow, and "Book this look" which opens booking with that exact service already chosen (on staging)
- 🟡 Follow like TikTok (visitors sign in first); "Saved shops" is now "Following" everywhere; follower counts on professionals (counts only) (on staging)
- 🟡 Admin rebuilt with a menu: Overview (members, growth chart, founding members, bookings and rates, recorded value, trust, engagement, training), Places (by country, city, area), Demand (most searched, opened, loved; "wanted but scarce" to guide recruiting; anonymous counts only), and every queue with badges (live backend; screens on staging)
- 🟡 Admin map: every shop on free OpenStreetMap (Leaflet), Ghana to street level, coloured live / waiting / restricted, pop-ups link to the shop (on staging)
- 🟡 Shop team and the chair card (Christopher's barbershop case: the master's helper serves customers when he's away, without being able to take them): owners add helpers by phone; per helper, "manage all bookings" and "see phone numbers" (off by default: •••• ••22); helpers open a customer's card only on the day of the visit (first name, past visits here and who served them, the shop's notes, saved style photos); every card opened is logged for the owner; notes belong to the shop, marked with the author; jobs record "served by"; leaving ends access instantly (live backend; screens on staging)
- 🟡 FRESH LOOK (upgrade chosen by Claude as the most-loved feature to build on): after a job, the shop (or the helper who served) adds a photo of the finished look within 14 days; it lands in the customer's "Your looks" (never replacing their own photo) and they're told; one tap makes a beautiful WhatsApp Status/Instagram Story card (photo, style, "by <shop>", place, price, "Book this look" link) that opens booking with that exact service; professionals get the same "Share to Status" card for every service with a photo; the brand name lives in one place for the rename; helpers' chair cards show the finished look (live backend; screens on staging)
- 🟡 Fixed: saved styles always showed "Style" instead of the service name (on staging)
- 🟡 LOOK REEL (Christopher's idea): 3 to 8 photos of one look (front, sides, back, even a "before") that play like a short video with soft fades and progress bars (tap to pause; still for reduced-motion users). Professionals add angles to any service or to a customer's finished look (14 days); Discover shows "▶ 5 angles" and loads the photos only when tapped (saves data); customers play their own looks' angles; "Share as video" makes an MP4 for WhatsApp Status on phones that can (otherwise the Fresh Look card). Reels live in their own records so shop records never outgrow the database limit; service reels are public, a customer's look reel is private to them and the shop (live backend; screens on staging)
- 🟡 FIELD WORK (Christopher's in-person growth plan, starting in his own area, then e.g. the Northern region's hand-beading): Admin → Field work → Trips: start a trip (name, area, region); log each shop visited with one hand at the door: location captured automatically, shop name, area, services (incl. beading and other crafts), outcome in one tap (signed up / interested / come back later / not interested), the craft's story (how it's done, where it comes from), optional phone, up to 4 photos only with the person's consent; stops save on the phone and upload by themselves when there's network (never duplicated); link a stop to the shop's Sheeba account once they sign up; per trip: stops, sign-ups, conversion, km covered, hours, route map. Coverage: every stop on one map beside shops already on Sheeba, results by region and area. New "Field agent" role for helpers who go out (live backend; screens on staging)
- 🟡 WHERE SIGN-UPS AND BOOKINGS COME FROM: each visitor's first touch (a professional's marketing link, an invite code, a shared "Book this look" card, a shop's own link, or arriving on their own, plus the website that sent them) is remembered on their phone for 30 days and recorded with their sign-up and bookings; "Book again" is its own source. Admin → Sources: sign-ups and bookings by source and channel, websites that sent people, best marketing links, shops whose shared links bring bookings, sign-ups from field work (live backend; screens on staging)
- 🟡 Marketing links finished: professionals make a separate link per channel (WhatsApp, Instagram, TikTok, Facebook, business card, flyer, direct message) in Share & earn and see each one's visits and bookings; link visits and bookings are now actually credited (on staging)
- 🟡 Review (28 Sep): only leftover code was removed (three old Discover components); payments and savings goals stay for later (Christopher: judge features by purpose, not by usage while he's the only tester)
- 🟡 Full test collection restored into the repo (tests/, `npm test`): 716 checks across 30 suites, all passing. Every failure found while restoring was an outdated test (stand-ins missing newer features, or sample data from designs Christopher deliberately changed), never an app bug; no app code was changed. Rule from now on: every feature ships with its test, and `npm test` must pass before any push to main
- 🟡 BADGES: "✓ Verified" is now "ID checked" (shield icon), a free safety signal meaning Sheeba confirmed the professional's ID. A future paid tier gets a DIFFERENT badge name ("Pro"/"Plus"/"Featured"); identity is never sold (Christopher, 28 Sep). Founding members (first 1,000) get a gold ring around their picture in the feed, shop page, My Shop and customer profile
- 🟡 "Likes", not "loves", everywhere (♥ icon kept)
- 🟡 ADMIN SWITCHES (all enforced on the server): age check; only ID-checked professionals on Discover; pause new sign-ups; pause new bookings; messages on/off (people pointed to call/WhatsApp); invite rewards on/off; a site-wide announcement banner (200 characters, closable per phone). A warning shows while anything is paused
- 🟡 Audit log grouped by week or month, filterable by admin and action, with readable action names (last 1,000 actions)
- 🟡 RETURN PATTERNS in Customers: "usually every N weeks", an "Expected back" list (due soon / overdue) from real completed visits (2+ visits needed, no guessing), and the shop's return rate
- 🟡 STUPIDLY SIMPLE PASS (29 Sep): (1) completed bookings have ONE button, "📸 Add photos of the finished look" (1 photo → the customer's styles; 3–8 → also plays as every side), replacing two buttons and the word "angles"; (2) "Share your shop" is one tap per place (WhatsApp, Instagram, TikTok, Facebook, flyer, somewhere else): Sheeba makes or reuses that place's link and opens sharing, with visits and bookings counted underneath (no dropdown, no naming); (3) "angles" is "photos" everywhere ("▶ 5 photos", "▶ See all photos", "▶ More photos"); (4) booking form steps numbered 1–4 consistently. Checked and left as they are: sign-up (name, phone, password, apprentice tick), the booking form's order, My Sheeba
- 🟡 THE ASSISTANT (🎤 in Search, 29 Sep): ask in plain words ("I'm at Koforidua, where do I find a makeup artist?", "I have 200 for locks", "barber near me", "GH₵150 nails East Legon") → a one-line answer plus real live professionals (photo, place, distance, the price that fits, ID-checked shield), nearest/cheapest first; says honestly when nobody is in that town and offers the nearest. Built-in understanding (free): every service and style incl. local words ("locks"), ~50 Ghana towns plus every area where shops are listed, budgets in any form, near me. AI (Claude Haiku) reads the question instead ONLY when an ANTHROPIC_API_KEY is set on Render AND Admin → Switches "Let AI read questions" is on; AI only extracts what was asked, answers always come from real listings; falls back to built-in if AI fails; 15 AI questions/15 min per address, 40 questions overall
- 🟡 "Apprentice" now reads "In training" / "trainee" everywhere people see it (20 places); the Terms keep "(apprentices)" beside the legal wording
- 🟡 FITS ANY SCREEN: on tablets and laptops Discover shows looks in a grid (2 across, 3 on wide screens), Search widens (photo grids up to 6 across), shop pages put services on the left and the booking form on the right (stays in view). Phones unchanged
- 🟡 SWIPE THROUGH A LOOK: opening a professional's look shows all its photos (swipe on phones, arrows on laptops, dots and "1/6"); extra photos load only when opened. Inspiration photos (Pexels) have one photo each
- 🟡 DISCOVER TOP: "☰ All services" opens every service as big tiles with how many professionals offer each (newly approved services appear automatically); the moving strip now shows "New on Sheeba" (newest professionals of the last 60 days, "Shop · Area"; tap opens them)
- 🟡 "📷 Add many at once" in Services: pick up to 10 photos (e.g. saved from Instagram/TikTok/WhatsApp), choose what each is (fills the name) and its price, add all; same limits as single adds (40 services, 14 MB)
- ⬜ LATER: official Instagram/TikTok import (needs Meta/TikTok app approval, usually a registered company)
- 🟡 INTEGRATION AUDIT (29 Sep), done by scripts in both directions: all 155 app calls reach a real server route (0 broken); every link goes to a page that exists (0 broken); every activity event that feeds a feature is read (Popular this week, earnings, Sources, check-in); server and app admin role lists have identical permissions. THREE HANGING PIECES FOUND AND CONNECTED: (1) NOTIFICATIONS: the server sent 36 kinds of alert but the new app had no bell: now a 🔔 with unread count in the top bar (refreshes every minute and on return), a Notifications page, "Mark all read", and tapping takes you straight to the right screen (My Shop ?tab= and Admin ?section= links; unknown sections fall back safely); (2) RATINGS could be stored but were never offered or shown: customers now rate a completed visit with one tap ("How was it? ★★★★★", once, only the customer who booked); shop pages show "★ 4.8 (12 ratings)" from 3 ratings up; the rating lookup can never break a shop page; (3) TELEGRAM COMMUNITY FEEDBACK was saved with no admin screen: now Admin → To do → Community feedback (badge count, mark handled), for super admins and Moderators, who also get its alerts
- 🟡 TELEGRAM, ANSWERED FROM ADMIN (29 Sep): Admin → Community feedback shows a plain status ("✓ Connected: @bot", or what's missing on Render) and a Connect button that hooks the bot to Sheeba itself (secret-protected, messages only); under each message an answer box posts the reply in the group AS A REPLY to that person; answers are saved with who answered; if Telegram refuses, nothing is marked answered. Needs on Render: TELEGRAM_BOT_TOKEN (from @BotFather) and TELEGRAM_WEBHOOK_SECRET; bot privacy mode off so it can read the group
- 🟡 SHARED SHOP LINKS LEAD INTO SHEEBA: a shop page opened from a link has no menu, so phones now get a bar at the bottom with "✨ Explore looks" and "Book"; larger screens get a filled "✨ Explore Sheeba" button (was a small outlined "Explore more shops")
- 🟡 TRAINEES: "Do this next" at the top of My Training picks the one right action (ask the supervisor to add skills; this week's focus; keep practising X and post a photo, with a 📸 button that jumps to posting)
- 🟡 TITLES THE TRADE USES (29 Sep): "professional" stays the umbrella word; each person shows the title for what they do, from their services, with no extra step: Hairdresser, Barber, Makeup artist, Nail technician, Lash & brow technician, Beauty therapist (new approved services: "<Service> specialist"); at most two ("Hairdresser · Makeup artist"). Shown on feed posts, professional cards, the look panel, shop pages, the assistant's answers, and My Shop profile ("Customers see you as…"). The last "stylist" wording is gone (a professional's message now notifies the customer "New message from <shop name>")
- 🟡 COUNTRY CHOICE, SIMPLE (29 Sep): one picker everywhere (sign-up, booking, settings, phone numbers): a button with the country's NAME (flags removed: many computers show them as two letters, e.g. "GH Ghana"), then a panel with "Type your country", likely countries first (yours, Ghana, Nigeria, UK, USA), every country by name in big rows; understands everyday names (UK, USA, Ivory Coast, Britain…); phone numbers show just "+233"
- 🟡 CONTINUE WITH GOOGLE (30 Sep): on both sign-in screens (professionals, customers), above the phone form, which stays for people without Google. First time: one short step for the phone number (Google doesn't give it), the age tick when the age check is on, and an opt-in for Mepluge news by email; it goes through the SAME sign-up as everyone (member number, code, invites, review for new shops), with a confirmed email and no password. Existing accounts: Settings → Google → connect. The server checks Google's signature itself (issued by Google, for Mepluge's key, not expired, confirmed email); forged/tampered/other-app/expired tokens refused (24 tests). Email and Google id never public. Admin overview counts confirmed emails and news opt-ins. Dormant until GOOGLE_CLIENT_ID is set on Render (Christopher: create the Google sign-in key)
- 🟡 PRIVACY FIX found while building it: public shop records no longer include where a professional signed up from (signupSource)
- 🟡 SPEED (30 Sep): Discover remembers its last list and shows it instantly when you come back (refreshing quietly); pages open the secure connection to the far-away server while loading. Known bigger causes, planned: photos travel inside the data (move to cloud storage with a CDN) and the server is in Ohio, USA (consider a region nearer Ghana, e.g. Frankfurt)
- 🟡 LOG OUT ASKS FIRST (30 Sep): both log-out buttons (Settings, Bookings) say "Log out" in calm colours (no longer red, which looked like deleting the account) and ask "Log out of Mepluge on this phone? You can log back in anytime…"
- 🟡 NEW NAME: MEPLUGE (Christopher, 30 Sep). Renamed everywhere people see it (app: 125 mentions in 54 files; server messages and their tests: 71), logo "ME·PLUGE" in the same two colours; internal names (storage keys, event names, the /my-sheeba address) deliberately unchanged so nobody loses saved settings or links. Temporary passwords now look like Mepluge-XXXX-XXXX. TO DO (Christopher): buy mepluge.com (nothing online uses the name), claim @mepluge on Instagram/TikTok/X/Telegram, register the business name; then point mepluge.com at the site
- ⬜ AFTER THE OLD SITE IS RETIRED: remove ~15 old-site routes the new app replaced (smaller attack surface). Parked on purpose: payments, savings goals. Small loose ends: delete a mistaken field-trip stop from the screen; let a customer claim bookings made before they had an account. Recorded-but-unused history events (account created, follow, rating, booking created, search, style saved) are kept for future analytics
- 🟡 SERVER MOVING TO FRANKFURT (30 Sep, plan reviewed): the server (Render, Ohio USA) and the database (Atlas free tier, Paris) were an ocean apart. New server "mepluge-api" created in Frankfurt (https://mepluge-api.onrender.com), same settings. SAFE ORDER: (1) Christopher copies the old server's environment variables to it (ideally via a Render Environment Group linked to both, so they never drift; JWT_SECRET identical so logins survive; a good moment to use a NEW Telegram token after /revoke) and sets Health Check Path /api/health; its first deploy failing before that is expected; (2) Claude verifies it; (3) only then Claude switches the app's one-line address (lib/serverAddress.js) to Frankfurt and pushes it to staging; the zip keeps the current server so it can be pushed any time. Old and new run side by side on the same database (no timed jobs). After release and retiring the old site: delete "sheeba-mavio", press Connect for Telegram, and consider limiting the database to Render Frankfurt's outbound addresses
- 🟡 SPEED: BROWSERS NOW REMEMBER PERMISSION (30 Sep review): app and server live at different addresses, so browsers ask permission (a "preflight") before most logged-in requests and forgot it after ~5 s: most taps made two ocean crossings. The server now tells them to remember for 2 hours. /api/health answers OK only when the database is connected (safe, zero-downtime updates). 5 tests
- ⬜ BEFORE REAL TRAFFIC: database backups (the free Atlas tier has none: move to a small paid tier), uptime monitoring with phone alerts, photos to cloud storage (free tier holds 512 MB). Database access list is open to all addresses (password-protected): tighten later
- 🟡 PHONE ALERTS WITH SOUND (Web Push, 30 Sep): every alert (all 36 kinds, e.g. "New booking request from Ama", "New message from Efua Glam") also reaches the person's phone(s) with the phone's own sound, even when Mepluge is closed; tapping opens Notifications. "Turn on alerts" on the Notifications page, in Settings, and as a nudge on My Shop's home (disappears once on); "Send me a test"; "Turn off". iPhone: shows the 3 steps to add Mepluge to the Home Screen first (Apple's rule). Keys are created once and kept privately by the server (nothing to set up); phones that uninstall are forgotten; max 10 phones per person; customer and professional alerts never mix (17 tests). Mepluge now installs to the Home Screen like an app (manifest, app icon: white M with a pink "plug" dot on violet)
- 🟡 PHONE ALERTS: PEOPLE CHOOSE (30 Sep, Christopher's feedback): nothing rings until someone turns alerts on; on turning them on they choose groups (Bookings, Messages, Looks and ratings, Team and training, Invites and rewards, Your account; Admin work for admins only), starting with Bookings, Messages and Your account; change any time in Settings. The in-app Notifications list still shows everything. Once alerts are on, the big card no longer shows on the Notifications page. Notifications grouped by day (Today, Yesterday, Earlier), unread marked by a thin pink edge (no uneven gap). Alerts saved before the rename now show "Mepluge". Choices kept in their own small table (AlertPref), accounts untouched. 10 tests
- 🟡 PHOTOGRAPHY IS A SERVICE (30 Sep): photographers join Mepluge as a service of their own, from launch: title "Photographer"; styles Wedding Shoot, Pre-wedding Shoot, Portrait Session, Graduation Shoot, Event Coverage, Studio Shoot; their work shows on Discover as cards with "Book this shoot"; the assistant understands "photographer for my wedding in Accra", "photoshoot for graduation under 500". Any other profession can still join by proposing its service (admin approves; it appears everywhere automatically)
- ⬜ POST-LAUNCH: MODELS (agreed 30 Sep). No separate sign-up: a customer switches on "Show my looks publicly" and "I'm available as a model" (18+ only). "Post a look": photos, style, tag the professional who did it; the professional confirms the tag ("✓ by <shop>"). Confirmed looks appear on Discover with "Book this look" → the tagged professional (real Ghanaian looks gradually replace Pexels inspiration). Public model page (photo, first name, area, looks, likes). Shops find models in Search (by town and style) and message them. Safety: models post only themselves, report button, admin removal, daily posting limit; comments later with moderation
- ⬜ POST-LAUNCH: CREDITS CARD (Christopher: "perfect", 30 Sep). From a customer's bookings for an occasion (wedding, birthday, graduation), Mepluge builds a shareable card listing everyone who worked on them with their role and handle (Hair, Makeup, Nails, Groom's cut…), plus people not on Mepluge added by name and handle (each invited to join). Professionals add their Instagram/TikTok handles to their profile once, so they're always right. Auto-written caption with every @handle, copied in one tap. Two sizes (WhatsApp Status, Instagram post), "Book them on mepluge.com". Every credited professional is told and, with permission, it shows on their shop page. Build together with Models (shared tagging and confirmation)
- ⬜ POST-LAUNCH: PHOTO CREDITS AND PHOTOGRAPHERS (30 Sep; relaxed by Christopher: "if I'm in the photo, I choose whether to recognise you"). "Photo by" is OPTIONAL on every upload: default is no credit, no prompts; the person posting decides. When someone does credit a photographer (on Mepluge, or a name and handle), the photo shows "📷 Photo: @handle" and credits cards get a Photos line; the photographer confirms credits made in their name (stops false claims) and can remove a false one. No policing of photos of yourself; the report button is for genuinely wrong cases (e.g. photos of other people posted without their knowledge); a specific photographer complaint is handled case by case by admin. Photographer becomes a profession (title "Photographer"; profile, portfolio, bookable for weddings, portraits, events); credited photos link to their page
- ⬜ NEXT (after go-live, agreed order): follow the stylist wherever they go (customers follow the person; the owner marks "no longer works here"; only the stylist's own followers are told); email login with self-service password reset (needs an email service, ideally on the new brand domain; marketing only with opt-in consent); My Glam Team (a customer's professional per service, shareable); customer public profiles and looks tagged with the stylist, with "Available as a model" (18+); customer ratings by professionals ("Highly rated customer"; details seen by professionals only; disputable); comments on looks (with moderation); French (follows the phone's language, not the country)
- ⬜ SECURITY HOMEWORK (Christopher): two-step login on GitHub, Render, Netlify, MongoDB Atlas and email; regular database backups before growth
- ⬜ Move photos and reels to cloud storage (Cloudflare R2 or Supabase Storage, both already connected) before real growth: today every photo lives in the database, fine for launch; also needed for the future video feed
- 🟡 Admin team roles: Christopher is super admin and can add people by phone as Verifier (shops, IDs, proposed services), Moderator (reports, restrictions, reading conversations for reports), Support (password help) or Analyst (insights and map, read only); roles are checked in the database on EVERY action, so removals take effect instantly and old login tokens grant nothing; the last super admin can never be removed; alerts go only to the admins who handle them; the audit log shows who did what; each admin's menu shows only their areas (live backend; screens on staging)

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
- 🟡 Style library: 6 services, 34 styles with other names for search; professionals can propose new services (built Round 2; on staging)
- 🟡 Inspiration photos: first 15 from Christopher's spreadsheet (Pexels, credited, labelled "Inspiration", served from Sheeba itself) (on staging); more to gather for barbering, makeup, nails, lashes
- 🟡 Professionals tag each service with a style, so every inspiration photo leads to people who actually do it (built Round 2; on staging)
- 🔨 Trending from real engagement: "Loved on Sheeba" (hearts) and "Popular this week" (shop visits) are real and on staging; per-style trending waits for the style library
- 🟡 Live Mode basics: featured strip drifts gently, pauses on hover, touch or focus, stops in search, never moves with reduced-motion settings (on staging)

## Phase 4 — Customer workspace

- 🟡 Customer accounts: register and log in (built, not yet tested on the new site)
- 🟡 My Sheeba: what's coming up, what's due (reminders with pause/remove), saved styles with photos and notes, invite code, account settings (built; held on hold/part1 until the combined release)
- 🟡 Appointments (customer): Upcoming and Past, shop names, dates, prices in the right currency; Book again, Save this style, Remind me (built; held on hold/part1 until the combined release)
- 🟡 Saved shops, and a Save shop button on every shop page (built; held on hold/part1 until the combined release)
- 🟡 PRIVACY HOTFIX, LIVE: "shops I follow" no longer sends shop owners' ID numbers, ID photos or legal names (deployed and verified by Claude; every other list route on the live server checked and found properly protected)
- 🟡 Customer privacy and safety fixes: Saved shops no longer sends shop owners' ID documents, legal names or phone numbers; nobody can follow as someone else; Save This Style photos must be real uploads; Book again has the same checks as booking; Remind Me intervals 1 week to 1 year (built; held on hold/part1 until the combined release)
- 🟡 Messages between customers and professionals: split view on larger screens, photos, refreshes every 10 seconds; only live shops can be messaged, restricted accounts can't send, limits against spam (on staging)
- 🟡 Customer QR check-in: a professional scans or types the customer's code and checks them in; the customer's name is shown ONLY if they already have an appointment together; the customer is notified and both see the check-in time; showing the code is the customer's consent (built; held on hold/part1 until the combined release)

## Phase 5 — Professional workspace

- 🔨 Home: today, pending requests, next actions (basic version live)
- 🟡 Real appointment dates: a Today view (who's coming, in time order, opens by default when someone's booked) and Upcoming grouped by day (built; held on hold/part1 until the combined release)
- 🟡 Calendar, day view: Today plus a by-day Upcoming list (built; held on hold/part1 until the combined release); a full week calendar comes later
- 🟡 Services: add, edit, hide, delete, with price, duration, description and a work photo (on staging)
- 🟡 Shop and profile editing: profile and cover photos, description, category, area, availability, GPS location, completeness checklist (on staging)
- 🟡 How I work: salon, home, mobile, by appointment (on staging)
- 🟡 Customers: everyone who has booked, due-for-next-visit list, full history, private notes (add and delete) (on staging)
- 🟡 Messages with customers, in My Shop (on staging)
- 🟡 Earnings: recorded service value by period and by service, new vs repeat customers, dated by completion; clearly not payments (on staging)
- 🟡 Sheeba code for every account (e.g. K7M 2QX): permanent for life across roles, random, never guessable; short link /u/CODE; QR to show, download, print for the salon and share on WhatsApp; older accounts get theirs automatically (built; held on branch hold/part1 until the combined release)
- 🟡 Invite rewards: GH₵1 when someone joins with your code and completes their first job; shown under Share & earn (professionals) and My Requests (customers); admin reviews each qualifying job, pays by hand and records the reference; flag when the inviter was on the job (built; held on branch hold/part1 until the combined release)
- 🟡 Apprentice and staff access: apprentices and staff see and work on the shop's requests, labelled "For <shop>" (on staging)
- 🟡 Trainee workspace (wireframe 08): My Training (progress, expected completion, this week's focus, skills the apprentice marks practising and only the supervisor signs off, feedback); supervisor's training editor with ready-made skill lists per service; graduation to independent professional keeping code and history; under-18s graduate at 18 (on staging)
- 🟡 Apprentice work progress: apprentices post photos of their work (optionally linked to a skill) for their supervisor to approve or send back with a comment; approving can also sign off the skill and show it on the shop page under "Our apprentices' work" (never for under-18s; first name and thumbnail only) (on staging)
- 🟡 Change password, for professionals and customers (on staging)

## Phase 6 — Admin control center

- 🔨 Separate admin environment (basic version live)
- 🟡 ID verification queue (built, not yet tested)
- 🟡 Shop review queue (see Phase 1)
- 🟡 Reports and restrictions: customers report professionals (shop page or any booking), professionals report customers they had a booking with; categories, emergency number first (112 Ghana / 999 UK), 5 per 15 minutes per address; admin queue with notes and states; restrict or restore customers AND professionals from a report, with a reason they're told
- 🟡 Password recovery: "Forgot password?" for everyone, admin help queue confirmed by calling the number on the account, temporary password that must be changed (on staging)
- 🟡 Password guessing stopped (5 wrong per account / 20 per address → 15-minute pause) and login no longer reveals whether a number has an account (LIVE, verified by Claude)
- ⬜ Public shop data still lists follower and like ID codes: show counts instead, keeping follow buttons working (scheduled with the switch to the new site) (low risk)
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
- 🟡 Full engineering review (27 Sep): 134 routes inventoried; dependencies audited (0 known vulnerabilities, backend and frontend); every internal link checked (none dead). Fixed: public shop records no longer reveal the admin account, minors, staff lists, restriction details or verification dates; public locations rounded to ~1 km (home-based professionals' front doors stay private; owners and admin still see exact); flood ceiling on anonymous follows/likes/visits (300 per 15 minutes per address, generous for shared mobile networks); anonymous bookings capped (20 per 15 minutes per address); customer names, savings goals and marketing links properly checked; reminders measured from completion (live backend, verified by Claude)
- ⬜ At the switch to the new site (needs the old site retired first): public shop data becomes an allow-list (only fields meant to be public); follower and like ID lists become counts; hide Group Points and "last active" from public records
- ⬜ Popularity that can't be faked: give logged-in accounts more weight than anonymous visitors in "Popular this week", "Loved on Sheeba" and ranking (anonymous counts can never be fully fake-proof)
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
