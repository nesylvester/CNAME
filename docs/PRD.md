# Unwind — Product Spec (v0.1, draft)

> Working title: **Unwind**. A calm, one-thumb "what should I watch tonight?" concierge that
> tracks new episodes across all your streaming subscriptions, briefs you at a set time,
> and deep-links you straight into the right app.

**Platform:** iOS first · **Market:** USA first · **Stage:** concept / wireframe

---

## 1. The one-line pitch
Most trackers are diaries for logging what you *watched*. Unwind is a concierge for deciding what to
watch *right now* — swipe-first, scheduled "unwind brief," and frictionless share-to-a-friend.

## 2. Who it's for
- Busy people with 4–7 subscriptions who feel decision fatigue ("what's even new?").
- Not-super-techy users (parents, older viewers) — must work on day one with zero setup pain.

## 3. The wedge (why us, not TV Time / Hobi / JustWatch)
1. **The scheduled "unwind brief"** — a time-aware digest ("3 new episodes, ~2h10m") when *you* unwind.
2. **One-handed, swipe-first deck** — thumb-zone UX; decide in seconds.
3. **Share an episode as a "suggested watch"** in one tap.
Existing apps do tracking + notifications; none combine these three into a calm, decisive flow.

## 4. Core constraints (designed-around, not bugs)
- **No in-app playback** of other services — we **deep-link** into Netflix/Max/etc. (industry standard).
- **Data, not scraping:** sit on top of TMDB / Trakt / JustWatch data; availability is **region-specific** (US v1).
- **"Link subscriptions"** = user selects services they own (to filter), not OAuth into each.

## 5. MVP (v1) — what ships first
- [ ] Onboarding: pick your services + set brief time + notification style (instant vs. batched)
- [ ] Track shows (search + add; import watchlist where possible)
- [ ] New-episode detection across owned services
- [ ] **Tonight screen** = the unwind brief (count, total runtime, per-show)
- [ ] **Swipe deck** = add to lineup / skip / open
- [ ] **Deep-link out** to the correct app + episode
- [ ] Push notifications (per-show on/off, batched digest at brief time)
- [ ] Share an episode link to a friend

## 6. Phase 2 (nice-to-have)
- Universal "Continue Watching" + universal watchlist across services
- "Leaving soon" expiry alerts
- Subscription cost-awareness ("unused 60 days → consider pausing")
- Shared/group watchlists, "watch together"
- Auto-detect what you watched (Simkl-style), voice brief, time-budget suggestions
- Offline/travel "pre-flight lineup" helper

## 7. UX principles (accessibility-first)
- Primary actions in the **bottom third** (thumb zone); nothing critical in top corners.
- Swipe gestures with a one-time coach overlay; learnable in ~5 seconds.
- Real text labels (not icon-only), high contrast, respect **Dynamic Type** / system text size.
- A single **"Just tell me what to watch"** button for decision-fatigue moments.
- Full VoiceOver labels; optional read-aloud brief.

## 8. Screens (see /wireframe/index.html)
- **Tonight** — the brief + new-for-you list + leaving-soon
- **Discover** — swipe deck
- **Watch (detail)** — deep-link buttons, download-for-offline hint, share
- **Setup** — services grid, brief time, notification style

## 9. Suggested tech (to discuss)
- **App:** SwiftUI (native iOS, best deep-linking + notifications + Dynamic Type).
- **Data:** TMDB (catalog/episodes) + JustWatch-style availability + optional Trakt account sync.
- **Backend:** lightweight service for change-detection + push (APNs); could start serverless.
- Wireframe here is plain HTML so you can open it on your phone before any Swift is written.

## 10. Open questions
- Free vs. paid? (Trackers often freemium — brief + sharing as premium?)
- How important is auto-detection vs. manual add for v1?
- Do we attempt watchlist import, or manual-add only at launch?

---
*This is a starting draft — meant to be argued with. Edit freely.*
