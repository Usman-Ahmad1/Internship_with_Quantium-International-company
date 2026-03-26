# Quantium Retail Analytics — Customer Behavior & Trial Store Evaluation

> **Analyzed 264,833 chip transactions across FY 2018–19 to uncover which customer segments drive sales — and evaluated whether a new in-store layout at 3 trial stores delivered enough uplift to justify a full network rollout.**

---

## The Business Problem

A major Australian supermarket chain needed answers to two questions:

1. **Who is actually buying chips — and what do they buy?**
   The category team needed to understand which customer segments drive the most revenue so they could target promotions and optimize shelf strategy.

2. **Does the new store layout work?**
   Three stores trialed a new in-store layout for 3 months. Before spending millions rolling it out chain-wide, leadership needed data-backed evidence it was actually moving the needle.

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

**1. Cleaning** — Removed duplicate records and filtered out bulk-buy outliers (e.g., single transactions with `PROD_QTY = 200` — clearly not a regular shopper).

**2. Formatting** — Converted Excel serial number dates into proper Python `datetime` objects for time-series analysis.

**3. Feature Engineering** — Extracted brand names and pack sizes from product name strings, enabling segment-level product preference analysis.

**4. Merging** — Joined transaction data with loyalty card data on `LYLTY_CARD_NBR` to connect purchasing behavior to customer segments.

---

## Task 1 — Who Buys Chips, and What Do They Buy?

### What the Data Shows

![Sales Trends](https://github.com/user-attachments/assets/a44c02d7-87c6-4f70-b9a2-94cec2b10634)

Sales followed a consistent seasonal pattern across FY 2018–19, with a clear **peak in January 2019** — likely driven by holiday/summer snacking — and **dips at end of August 2018 and June 2019**, coinciding with end-of-financial-year periods. Revenue held steady overall, indicating a healthy, stable category.

---

### Customer Segment Breakdown

![Customer Segments](https://github.com/user-attachments/assets/2f9e5a2b-5925-480d-9507-70d13ffbfc34)

| Segment | Key Metric | Value | What It Means |
|---------|-----------|-------|---------------|
| Older Families — Budget & Mainstream | Total revenue & transactions | Highest in category | These are the **volume engine** — any promotion targeting them moves category-level numbers |
| Young Families | Avg. annual spend per customer | **$34.69** | The **highest-value customers** per head — worth protecting through loyalty programs |
| Mainstream customers (all ages) | Share of total customer base | **40.3%** (29,245 customers) | The largest single tier — a prime target for broad-reach campaigns |
| Mainstream Young Singles/Couples | Avg. transaction value | **$7.56** | Highest per-transaction spend — likely buying premium or larger packs |
| Budget Young Singles/Couples | Avg. annual spend | **$16.18** | Lowest annual spend — price-sensitive, respond better to value offers |

---

### Product Preferences (Consistent Across All Segments)

- **Dominant pack size:** 175g — the category anchor and top seller in every segment
- **Dominant brand:** Kettle — leads across all customer tiers without exception

**So what?** Stockouts on 175g Kettle products carry outsized risk. If a store runs low, they're losing sales from their highest-revenue customers.

---

## Task 2 — Does the New Store Layout Work?

### Trial Setup

- **Trial period:** February – April 2019 (3 months)
- **Trial stores:** 77, 86, 88
- **Matched control stores:** 233, 155, 237 (paired based on pre-trial sales, customer count, and transaction volume)

Each trial store was compared against a control store with nearly identical historical performance — isolating the layout change as the variable being tested.

---

### Results

![Trial Store Comparison](https://github.com/user-attachments/assets/2d26c704-09b0-49e3-9398-2c44acb037f5)

All three trial stores **outperformed their matched controls** across every key metric during the trial window.

| Trial Store | Control Store | Sales Uplift | Unique Customer Uplift |
|-------------|---------------|:------------:|:----------------------:|
| **Store 77** ⭐ | Store 233 | **+29.13%** | **+23.48%** |
| Store 86 | Store 155 | Positive | Positive |
| Store 88 | Store 237 | Positive | Positive |

**Store 77 was the standout.** A 29% sales uplift and 23% increase in unique customers visiting suggests the new layout is not just driving larger baskets — it's attracting customers who weren't buying chips before. That's a meaningful signal.

---

### The Statistical Caveat — and Why It Matters

```
p-value > 0.05  →  Results do not reach formal statistical significance
```

This does **not** mean the layout failed. It means 3 months of data is not enough to rule out random variation with confidence.

Think of it this way: the direction is strong and consistent across all three stores, but the sample window is too small to be certain the layout — not some other factor — caused the uplift.

**The right call is not to stop. It's to gather more data before going all-in.**

---

## Strategic Recommendations

### 1. Run Promotions at Your Volume Drivers
Target **Older Families (Budget & Mainstream)** for volume-based promotions. They generate the most transactions in the chips category — even a small lift in their purchase frequency moves total revenue significantly.

### 2. Protect Your High-Value Segment
**Young Families** spend $34.69 per customer annually — the highest of any segment. Invest in loyalty and retention here. Losing these customers costs more than their size suggests.

### 3. Don't Let Kettle 175g Run Out
**175g Kettle** is the consistent top choice across every segment. Stockouts on this product hit revenue across the entire customer base. Prioritize availability and front-of-shelf placement in all stores.

### 4. Extend the Trial Before Full Rollout

The new layout shows **strong directional uplift** — especially Store 77 at +29.13% sales — but the 3-month window is statistically insufficient.

**Recommended action plan:**

| Step | Action |
|------|--------|
| ✅ Now | Continue the layout in trial stores — results are positive, no reason to revert |
| 📅 Next 3–6 months | Extend the observation window to accumulate sufficient data |
| 📊 Month 6 | Re-run significance testing with expanded data |
| 🚀 If significant | Proceed with phased network rollout, starting with stores most similar to Store 77 |

Rolling out to the full network before reaching significance risks spending significant capital on a change that may partly reflect seasonal variance rather than layout impact.

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

## Key Takeaways

| # | Insight | Decision |
|---|---------|----------|
| 1 | Older Families drive category volume | Prioritize in promotions |
| 2 | Young Families are highest per-customer value | Invest in retention |
| 3 | Kettle 175g dominates all segments | Protect availability chain-wide |
| 4 | Trial layout shows strong uplift (up to +29%) | Extend observation before full rollout |

---

*Completed as part of the Quantium Data Analytics Virtual Experience Program (Forage) — FY 2018–19 data.*
