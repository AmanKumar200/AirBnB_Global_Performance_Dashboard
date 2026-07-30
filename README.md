## 📊 Global Airbnb Performance Dashboard — Data Analysis

An end-to-end Power BI analysis of Airbnb activity across 10 global cities, covering supply growth, market concentration, guest ratings, review behavior, seasonality, and host trust signals.

**📁 Power BI file (.pbix):** [Download from Google Drive](https://drive.google.com/file/d/1k0C-K6869JV95htBKb9llOZDLhaIvQb7/view?usp=drive_link)

---

### Dataset Snapshot

| Metric | Value |
|---|---|
| Total Listings | 280K |
| Cities Covered | 10 |
| Hosts | ~182K |
| Property Types | 144 |
| Reviewers | 5.37M |

---

## Dashboard Walkthrough

The report is built as four pages. Each is explained below in the order they appear in the PDF export — add your own screenshot for each under `/assets` and update the image paths.

### Page 1 — Growth Story: Launch to COVID-19

<img width="1082" height="797" alt="Screenshot 2026-07-30 150657" src="https://github.com/user-attachments/assets/525ae563-c256-4bb6-b469-30ff028ce707" />

This page tracks total listings from 2008 to 2021, segmented into six lifecycle phases: **Introduction, Growth, Maturity, Decline, Reinvention, and COVID-19.**

**What it shows:**
- Listings took off after 2010 and peaked around 2015 — the single highest year for new listings.
- 2016–2017 growth flattened, coinciding with **local regulatory tightening** in several cities — supply growth stalled even though the platform hit **profitability** in the same window (first full profitable year: 2017).
- A modest recovery ("Reinvention") began around 2018–2019, before **COVID-19 erased nearly all listing volume by 2020–2021.**

**Read on this:** growth and profitability moved in opposite directions during 2016–2017. That's worth noting on its own — expansion was not the thing driving the business into profit.

---

### Page 2 — City-Level Performance & Guest Ratings

<img width="1070" height="784" alt="Screenshot 2026-07-30 150721" src="https://github.com/user-attachments/assets/21c64769-fa32-46e8-b9f3-5e42b6416474" />


A Pareto (80/20) view of listings by city, paired with a price comparison and a city ratings ranking.

**What it shows:**
- **Paris, New York, and Sydney together account for roughly half of all listings and 48% of all reviews.** Paris alone holds 23.1% of listings — the single largest concentration in the dataset.
- Average nightly price comparison: Hotel room **$800** vs. Airbnb entire place **$673**, shared room **$580**, private room **$462**. The dashboard frames Paris's dominance as possibly linked to this price gap — that's a **hypothesis worth testing**, not a proven cause. City size, tourism volume, and marketing spend are all uncontrolled variables here.
- Rating range across cities runs from **89.7 (Hong Kong, lowest)** to **94.8 (Mexico City, highest)** — a meaningful ~5-point spread on what should be a fairly narrow scale.

---

### Page 3 — SuperHost Distribution & Category Ratings

<img width="1070" height="786" alt="Screenshot 2026-07-30 150733" src="https://github.com/user-attachments/assets/9a2b97b5-7fb0-47a1-91a3-19ad7720303c" />

Same city-concentration chart, this time split by SuperHost vs. non-SuperHost listings, plus a detailed ratings breakdown by category (Accuracy, Cleanliness, Communication, Location, Value).

**What it shows:**
- **Cleanliness and Value-for-money are the two lowest-scoring categories across nearly every city** — this is consistent, not a one-off. It's a specific, fixable operational gap rather than a vague "ratings are low" observation.
- Hong Kong and Istanbul underperform across *most* categories, not just one — suggesting a broader service quality issue in those markets rather than a single weak metric dragging the average down.

---

### Page 4 — Review Behavior, Seasonality & Trust

<img width="1069" height="789" alt="Screenshot 2026-07-30 150757" src="https://github.com/user-attachments/assets/680efce5-7d32-4b4e-9a75-e282bc644eed" />

Three panels: how often guests leave reviews, when reviews peak by city and month, and host trust/verification signals.

**What it shows:**
- **98.8% of reviewers left 3 or fewer reviews total** — most guests are one-and-done reviewers, not repeat platform users. Review count is a weak proxy for guest loyalty.
- One reviewer logged 283 reviews, with the last two posted the same day for two different Bangkok listings. The dashboard itself flags this as a likely data error — **this record should be investigated and probably excluded** before this chart is used to support any claim about guest behavior.
- ⚠️ **Data quality note:** the cumulative-percentage line on this chart shows values like 474.8% and over 1,000,000% once it reaches the outlier categories (283, 96 reviews). That's not a real result — it's a calculation bug, most likely from treating irregular review-count values as sequential x-axis categories. Flagging this here so it doesn't get mistaken for an insight — it needs a fix in the underlying measure before this page is shared externally.
- **Seasonality:** Paris and Rome dominate review share from April–August (European summer travel). New York spikes in November–December (holiday season). Seasonality is city-specific, not global.
- **Trust:** 66.9% of hosts are fully identity-verified with a profile picture. Only 0.4% of hosts show zero trust signals at all. The main opportunity is the **32.6% of hosts who have a profile picture but aren't identity-verified** — the highest-leverage group to convert.

---

## Key Takeaways

1. **Growth is regulation-capped, not demand-capped.** The 2016–2017 slowdown lines up with policy tightening, not falling demand — expansion strategy needs to be policy-aware per market, not just supply-driven.
2. **Revenue is concentrated in 3 cities.** Paris, NYC, and Sydney carry a disproportionate share of listings and reviews — a market-level shock in any one of them has an outsized effect on the whole platform.
3. **The price-gap-vs-hotels story is a hypothesis, not a proven driver.** It's a reasonable positioning angle, but shouldn't be treated as a confirmed cause of Paris's lead without controlling for other factors.
4. **Cleanliness and value-for-money are the recurring weak points**, not an isolated city issue — this points to an operational/training fix, not a marketing one.
5. **Review count is a poor loyalty metric** — with 98.8% of guests reviewing 3 times or less, repeat engagement needs a better measure than review frequency.
6. **Trust infrastructure is already strong** (67% fully verified), so the highest-ROI action is converting the 33% "profile pic only" segment, not building new trust features from scratch.
7. **Seasonality is city-specific.** A single global marketing calendar is leaving performance on the table in at least two clearly different seasonal patterns (Southern Europe summer vs. NYC winter holidays).

---

## Business Recommendations

| Insight | Recommended Action |
|---|---|
| Regulation stalled 2016–17 growth | Build regulatory review into market-expansion planning *before* entering a city, not after |
| 3 cities hold ~half of listings/reviews | Actively diversify supply into mid-tier cities to reduce concentration risk |
| Price-gap vs. hotels is unproven as a cause | Run a controlled test (e.g., price elasticity or booking-conversion analysis) before using this as a core positioning claim |
| Cleanliness & value scores lag everywhere | Launch a targeted host-quality program (audits, cleaning standards, pricing guidance) starting in Hong Kong and Istanbul |
| 32.6% of hosts are profile-pic-only | Run a targeted ID-verification incentive campaign for this segment specifically |
| Reviews cluster seasonally by city | Shift marketing/pricing calendars to be city-specific — e.g., Paris/Rome push in Apr–Aug, NYC push in Nov–Dec |
| Outlier reviewer + broken cumulative-% chart | Clean the 283-review record and fix the cumulative-% measure before this report is used for decision-making or shared externally |

---

## Data Quality & Limitations

- **10 cities only.** The title says "Global," but the dataset covers a specific set of 10 cities — findings shouldn't be generalized beyond them without more data.
- **One known outlier record** (283 reviews from a single reviewer, two same-day reviews) needs investigation before being included in guest-behavior conclusions.
- **One known chart bug**: the cumulative-percentage line on the Review Frequency chart produces invalid values at the outlier x-axis categories and needs a fix.
- **Correlation vs. causation**: the hotel-price-vs-listings-share relationship on Page 2 is descriptive, not causal.

---

## Tools Used

- **Power BI Desktop** — data modeling, DAX measures, Power Query transformations, report design
- Full interactive `.pbix` file linked at the top of this section for anyone who wants to explore the model or rebuild these visuals
