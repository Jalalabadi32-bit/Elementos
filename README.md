# CivicRank — City Reputation System

> **Track 3 Initiative** · A transparent, city-wide moral reputation platform that recognizes good citizens and holds repeat offenders accountable.

---

## Overview

CivicRank is a single-page web application that simulates a city-wide citizen reputation system. Citizens earn and lose reputation points through civic actions, official assessments, and peer endorsements. The system divides the population into five moral tiers — from **Exemplar** at the top to **Flagged** at the bottom — with a deliberately asymmetric scoring curve that makes it harder to reach the highest tiers and progressively harsher for repeat offenders.

The frontend is a fully self-contained `civicrank.html` file with no external dependencies beyond Google Fonts. All data is hardcoded for demonstration purposes.

---

## Features

### 🏠 Landing Page
- Hero section introducing the CivicRank concept with a live tier preview stack
- Animated "live" indicator showing the system is active
- City-wide statistics: total registered citizens, points awarded, and peer endorsements
- Navigation links and a prominent login CTA

### 🔐 Authentication
- Modal login flow with Citizen ID + Passphrase
- Four pre-built demo accounts covering the full tier spectrum
- Click-to-autofill for quick demo access
- Backdrop-click to dismiss

### 📊 Citizen Dashboard
Once logged in, each citizen sees a personalized dashboard with:

**Reputation Overview**
- Large, color-coded total score
- Month-over-month change indicator
- Current tier card with tier description and points needed to advance
- Full score breakdown: Official Points (70%), Peer Points (30%), Civil Service Bonus, Repeat Offence Penalty

**Tier Standings**
- All five tiers displayed in a grid
- Current tier highlighted with a color border and `◀ YOU` indicator

**Peer Endorsement Panel**
- Award positive or negative peer points to connected citizens
- Points are applied live and the dashboard re-renders immediately
- Capped at 50 points per transaction to prevent abuse

**Recent Activity Feed**
- Timestamped log of all scoring events
- Categorized by type: Official Positive, Official Negative, Peer Endorsement
- Icons and color-coded point values

**Peer Network**
- Displays connected citizens with their tier and score
- Tier color-coded avatars

**City Leaderboard**
- Top 10 citizens ranked by score
- Current user's rank highlighted
- Tier badge displayed for each citizen

---

## Scoring System

### Point Sources

| Source | Weight | Description |
|---|---|---|
| Official Points | 70% | Awarded by city authorities for civic actions and violations |
| Peer Points | 30% | Awarded or deducted by fellow citizens |

### Civil Service Bonuses
Major positive contributions trigger a significant bonus multiplier on top of the base points. Examples include organizing a community blood drive, running a literacy program, or leading a neighbourhood patrol.

### Repeat Offence Escalation
Each repeated violation adds a compounding penalty. A first-time minor offence deducts a small number of points. A third offence of the same type deducts substantially more, reflecting the system's zero-tolerance stance on habitual misconduct.

### Tier Structure

| Tier | Name | Score Range | Description |
|---|---|---|---|
| Ⅰ | Exemplar | 2000+ | Exceptional civic leadership and consistent moral standing |
| Ⅱ | Upstanding | 1000–1999 | Regular positive contributions and strong peer recognition |
| Ⅲ | Civic | 400–999 | Active participation in community life |
| Ⅳ | Standard | 0–399 | General population standing |
| Ⅴ | Flagged | Below 0 | Under civic review; remediation required |

The scoring bar becomes **less sensitive** as citizens approach the top tiers — larger point gains are needed to advance through Tier Ⅱ and Ⅰ than through the lower tiers. This prevents gaming the system and ensures the highest tiers represent genuine, sustained civic excellence.

---

## Demo Accounts

All accounts use the password: `civic2024`

| Citizen ID | Name | Tier | Score | Notes |
|---|---|---|---|---|
| `ADA-7741` | Adaora Nwosu | Exemplar | 2,480 | Organized blood drives, youth mentorship, neighbourhood patrol |
| `KIR-3302` | Kiran Mehta | Upstanding | 1,340 | Food bank volunteer, reported illegal dumping |
| `MRC-5510` | Marcos Ferreira | Civic | 612 | Park clean-ups, civic voting participation |
| `LIN-9920` | Lina Vasquez | Flagged | −180 | 3rd repeat minor offence; mandatory community service assigned |

---

## Tech Stack

| Layer | Choice |
|---|---|
| Structure | Vanilla HTML5 |
| Styling | Pure CSS3 with custom properties |
| Logic | Vanilla JavaScript (ES6+) |
| Fonts | Cormorant Garamond, DM Mono, Bebas Neue (Google Fonts) |
| Dependencies | None (zero npm, zero frameworks) |

The entire application ships as a single `.html` file. Open it in any modern browser — no build step, no server required.

---

## Running Locally

```bash
# No installation needed. Just open the file.
open civicrank.html

# Or serve it with any static file server:
npx serve .
python3 -m http.server 8080
```

---

## Project Structure

```
civicrank.html        # Complete self-contained application
README.md            # This file
```

---

## Design Decisions

**Obsidian + Gold palette** — Conveys institutional authority and civic seriousness without feeling dystopian. Gold accents reward top-tier citizens visually.

**Asymmetric tier thresholds** — Lower tiers have smaller gaps (0→400, 400→1000) while the top tier requires a large sustained effort (1000→2000+). This mirrors how genuine civic trust is hard to earn and easy to lose.

**Peer points capped at 30%** — Prevents coordinated manipulation by social groups while still making community recognition meaningful. No single peer endorsement can dramatically shift a score.

**Compounding penalties** — Repeat offenders don't just accumulate flat negative points; each recurrence hits harder. This reflects the real-world principle that habitual misconduct is more serious than isolated incidents.

---

## Future Scope

- Backend integration with a city database and real identity verification
- Admin panel for municipal officers to award civil service bonuses
- Appeal mechanism for citizens to contest unfair deductions
- Anonymized aggregated data dashboard for city planning
- Push notifications for score changes and tier transitions
- Integration with public services (library access, transit discounts) based on tier

---

## License

Built for the **Track 3 Civic Innovation Initiative**. Demonstration use only.
