# Quantium Retail Analytics — Customer Behavior & Trial Store Evaluation

> Analyzed **264,833 chip transactions** across FY 2018–19 to identify the highest-value customer segments and determine whether a new in-store layout across 3 trial stores drove enough sales uplift to justify a full network rollout.  
> **Top finding: Store 77 delivered +29% sales and +23% new customers under the new layout — but 3 months of data isn't enough to go all-in. Here's the full picture.**

---

## Key Insights

- 🏆 **Older Families (Budget & Mainstream) are the volume engine** — they generate the most transactions in the chips category. Any promotion targeting them moves category-level numbers.
- 💰 **Young Families spend the most per customer ($34.69/year)** — a small retention investment here protects disproportionate revenue.
- 📦 **175g Kettle dominates every segment** — stockouts on this single SKU create the highest revenue risk across the entire customer base.

---

## Results at a Glance

| Metric | Result |
|--------|--------|
| Total FY 2018–19 Revenue | $1,933,109 |
| Total Transactions Analyzed | 264,833 |
| Top Revenue Segment | Older Families — Budget & Mainstream |
| Highest Spend Per Customer | Young Families ($34.69/year) |
| Best Trial Store Uplift | Store 77 — **+29.13% sales**, **+23.48% unique customers** |
| Statistical Conclusion | Directionally strong; extend to 6+ months for significance |

---

## Tools & Technologies

| Category | Details |
|----------|---------|
| Language | Python 3 |
| Libraries | pandas, NumPy, Matplotlib, SciPy |
| Statistical Method | Independent samples t-test |
| Environment | Kaggle Notebooks (Jupyter-based) |
| Data Formats | Excel `.xlsx`, CSV `.csv` |

---

## Dataset & Data Pipeline

### Source Files

| File | Description |
|------|-------------|
| `Quantium data.xlsx` | Transaction-level purchase records |
| `QVI_purchase_behaviour.csv` | Customer loyalty card segmentation |
| `QVI_data.csv` | Final merged & enriched dataset |

### How the Data Was Prepared

**1. Cleaning** — Removed duplicates and filtered bulk-buy outliers (e.g., `PROD_QTY = 200` — not a regular shopper).

**2. Formatting** — Converted Excel serial number dates into proper Python `datetime` objects for time series analysis.

**3. Feature Engineering** — Extracted brand names and pack sizes from product name strings, enabling segment-level product preference analysis.

**4. Merging** — Joined transaction data with loyalty card data on `LYLTY_CARD_NBR` to connect purchasing behavior to customer segments.

---

## Task 1 — Who Buys Chips, and What Do They Buy?

### Sales Trends

![Sales Trends](https://github.com/user-attachments/assets/a44c02d7-87c6-4f70-b9a2-94cec2b10634)

Sales followed a consistent seasonal pattern across FY 2018–19, with a clear **peak in January 2019** (holiday/summer snacking) and **dips at end of August 2018 and June 2019** (end of financial year periods). Revenue remained stable overall — a healthy, well-established category.

---

### Customer Segment Breakdown

![Customer Segments](https://github.com/user-attachments/assets/2f9e5a2b-5925-480d-9507-70d13ffbfc34)

| Segment | Key Metric | Value | What It Means |
|---------|-----------|-------|---------------|
| Older Families — Budget & Mainstream | Total revenue & transactions | Highest in category | Volume engine — promotions here move category numbers |
| Young Families | Avg. annual spend per customer | **$34.69** | Highest-value customers per head — worth protecting |
| Mainstream customers (all ages) | Share of total customer base | **40.3%** (29,245 customers) | Largest single tier — prime target for broad campaigns |
| Mainstream Young Singles/Couples | Avg. transaction value | **$7.56** | Highest per-transaction spend — buying premium/larger packs |
| Budget Young Singles/Couples | Avg. annual spend | **$16.18** | Lowest annual spend — price-sensitive, respond to value offers |

---

### Product Preferences (Consistent Across All Segments)

- **Dominant pack size:** 175g — the category anchor and top seller in every segment
- **Dominant brand:** Kettle — leads across all customer tiers without exception

**Implication:** Stockouts on 175g Kettle products carry outsized revenue risk. Prioritize availability and front-of-shelf placement across all stores.

---

## Task 2 — Does the New Store Layout Work?

### Trial Setup

- **Trial period:** February – April 2019 (3 months)
- **Trial stores:** 77, 86, 88
- **Matched control stores:** 233, 155, 237 — paired on pre-trial sales, customer count, and transaction volume

Each trial store was compared against a control store with nearly identical historical performance, isolating the layout as the variable being tested.

---

### Results

![Trial Store Comparison](https://github.com/user-attachments/assets/2d26c704-09b0-49e3-9398-2c44acb037f5)

All three trial stores outperformed their matched controls across every key metric.

| Trial Store | Control Store | Sales Uplift | Unique Customer Uplift |
|-------------|---------------|:------------:|:----------------------:|
| **Store 77** ⭐ | Store 233 | **+29.13%** | **+23.48%** |
| Store 86 | Store 155 | Positive | Positive |
| Store 88 | Store 237 | Positive | Positive |

**Store 77 was the standout.** A 29% sales uplift alongside a 23% increase in unique customers suggests the layout isn't just growing basket size — it's bringing in customers who weren't buying chips before.

---

### Statistical Caveat

```
p-value > 0.05  →  Results do not reach formal statistical significance
```

This does **not** mean the layout failed. It means 3 months of data is too short to rule out random variation with confidence. The direction is strong and consistent across all three stores — the sample window just needs to be wider before committing capital to a full rollout.

---

## Strategic Recommendations

### 1. Run Targeted Promotions on Your Volume Drivers
**Action:** Launch bundle or multi-buy promotions aimed at **Older Families (Budget & Mainstream)** — e.g., "2 for $X" on 175g packs. Even a 5% increase in their purchase frequency delivers measurable category revenue growth.

### 2. Protect Your Highest-Value Customers
**Action:** Introduce a loyalty mechanic specifically for **Young Families** — points multipliers, early access to new flavors, or personalized offers. At $34.69 per customer annually, losing 500 of these customers costs ~$17,000 in revenue. Retention here is cheap compared to acquisition.

### 3. Make 175g Kettle Stockout-Proof
**Action:** Set a **minimum stock threshold** for 175g Kettle across all stores and flag replenishment automatically before shelves run low. This is the single SKU that, if out of stock, reduces sales across every customer segment simultaneously.

### 4. Extend the Trial — Then Decide on Full Rollout
The layout shows real promise, but 3 months isn't a sufficient basis for a network-wide capital decision.

| Step | Action | Timeline |
|------|--------|----------|
| ✅ Keep the layout in trial stores | Results are positive — no reason to revert | Now |
| 📅 Extend observation window | Accumulate 6+ months of post-layout data | Next 3–6 months |
| 📊 Re-run significance testing | Determine if uplift holds across seasons | Month 6 |
| 🚀 Phased rollout if significant | Start with stores most similar to Store 77 profile | Month 7+ |

**Bottom line:** The data points in the right direction. Don't roll back — but don't roll out to the full network until the numbers are statistically defensible.

---

## Project Structure

```
quantium-retail-analytics/
│
├── data/
│   ├── Quantium data.xlsx              # Raw transaction data
│   ├── QVI_purchase_behaviour.csv      # Customer loyalty segmentation
│   └── QVI_data.csv                    # Final merged & enriched dataset
│
├── notebooks/
│   ├── task1_customer_analysis.ipynb   # Customer behavior analysis
│   └── task2_trial_evaluation.ipynb    # Trial store performance evaluation
│
├── visuals/
│   ├── sales_trends.png
│   ├── segment_revenue.png
│   └── trial_store_comparison.png
│
└── README.md
```

---

*Completed as part of the Quantium Data Analytics Virtual Experience Program (Forage) — FY 2018–19 data.*
