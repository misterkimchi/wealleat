# WeAllEat (WAE)

> **Nobody deserves to go hungry. That's our WAE.**

WeAllEat connects businesses that have extra food (restaurants, grocers, caterers, campus dining) with nearby shelters and community kitchens that can use it right away, and lets neighbors reserve a free meal close to home.

**UN SDG:** 1 – No Poverty *(confirm against your team email)*
**Program:** Mentor Me Collective × Google Cloud Launchpad, BUILD 2026

---

## The problem

Good food gets thrown away every day while people nearby go without. The hard part isn't goodwill. It's logistics:

- Donors have a short window before food has to be tossed, and no quick way to find someone who can take it **now**.
- Kitchens can only accept food they can **store** (cold, hot, dry, frozen), have **room** for, and can **reach in time**.
- Handoffs get lost: nobody confirms the food actually changed hands.

*(Add your research and sources here: local food-waste numbers, shelter interviews, etc.)*

## What it does

| Who | What they can do |
|---|---|
| **Donor** | Post a batch in under a minute (storage type, servings, allergens, pickup cutoff up to 2 hours). See which kitchen is coming and call them. Check the kitchen's 4-digit PIN at pickup. |
| **Kitchen / shelter** | See only food it can store, has room for, and can reach in time. Reserve it, choose a pickup time, and confirm the handoff with a PIN. Serve walk-ins and hand out reserved meals. |
| **Neighbor** | See meals being served nearby within their chosen mile radius, hold a few servings, and show a code at pickup. |
| **Staff** | A short "needs your help" list: repeated PIN lockouts, food nobody can take, and support tickets. |

### Design rules we hold to

- **Rule-based matching only.** A kitchen is offered food only if its storage, open capacity, distance radius and travel time all fit. No AI decides whether food is safe or who gets it.
- **Every handoff is confirmed in person** with a 4-digit PIN (3 tries, then a lock).
- **People can fix most problems themselves** (new PIN once, automatic re-offer when a kitchen cancels, holds that expire automatically), so it works even without staff on hand.

### Batch lifecycle

`AVAILABLE → RESERVED → HANDOFF_CONFIRMED`, with `EXPIRED`, `CANCELED` and `UNMATCHED` as end states.

## Current status

| Part | Status |
|---|---|
| Clickable prototype (all four roles, matching, PINs, holds, walk-ins, help center) | ✅ Done: `src/web/index.html` |
| Real accounts and saved data (Google Cloud) | 🔲 Planned, see [docs/architecture.md](docs/architecture.md) |
| NVIDIA model feature | 🔲 Planned, see [docs/architecture.md](docs/architecture.md) |
| Real address → distance | 🔲 Planned (prototype uses simulated locations) |

The prototype runs entirely in the browser with sample data: 5 donors, 5 kitchens and 20 batches. Accounts you create only last until the page reloads.

## Run it

No install needed:

1. Download or clone this repo.
2. Open `src/web/index.html` in any browser.
3. Pick a role and click **Use demo account**, or create a test account.

The yellow **Demo** button (bottom-left) lets you move the clock forward and trigger test cases such as a PIN lockout, a missed pickup and an expiring batch.

## Google Cloud + NVIDIA

*(Fill in as these are built. Say where each one fits, show it in the demo, and explain how to reproduce it.)*

- **Google Cloud:** …
- **NVIDIA:** …

API keys live in server-side secrets only. Never commit them. See `.env.example`.

## Team

| Name | Track | Focus |
|---|---|---|
| Chad Kim | | Matching rules and app architecture |
| Scott Li | | Security, PINs and sign-in |
| Gerson Boch | | Infrastructure and timers (holds, expiry) |
| Babafemi Ajetunmobi | | AI and user experience |

*(Fill in each person's GCLP track and their individual contributions.)*

## Links

- Demo video: *(add)*
- Presentation deck: *(add)*
- Written summary: *(add)*

## Future ideas

- Real address lookup, with live traffic shown as information only (never used for matching).
- Text-message alerts when food is posted nearby.
- Donor tax receipts and monthly impact reports.
- Better impact numbers: food weight from meals (about 1.2 lb per meal) and emissions avoided, using published factors.

## License

[MIT](LICENSE)
