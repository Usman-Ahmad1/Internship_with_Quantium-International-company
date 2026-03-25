 **A data-driven portfolio project analyzing customer purchasing behavior and evaluating a new in-store layout trial for a major Australian supermarket chain.**

---

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Tools & Technologies](#tools--technologies)
- [Dataset & Data Pipeline](#dataset--data-pipeline)
- [Task 1 — Customer & Purchasing Behavior Analysis](#task-1--customer--purchasing-behavior-analysis)
- [Task 2 — Trial Store Performance Evaluation](#task-2--trial-store-performance-evaluation)
- [Strategic Recommendations](#strategic-recommendations)
- [Project Structure](#project-structure)

---

## 📌 Project Overview

This project was completed as part of the **Quantium Data Analytics Virtual Experience Program**. It addresses two core business problems for a major Australian supermarket chain:

| Task | Objective |
|------|-----------|
| **Task 1** | Understand which customer segments drive chips category sales and identify key product preferences |
| **Task 2** | Evaluate whether a new in-store layout trialed at select stores performed well enough to justify a full network rollout |

**Business Period Covered:** FY 2018–19

---

## 🛠️ Tools & Technologies

| Category | Details |
|----------|---------|
| **Language** | Python 3 |
| **Libraries** | pandas, NumPy, Matplotlib, SciPy |
| **Statistical Method** | Independent samples t-test (trial significance testing) |
| **Environment** | Kaggle Notebooks (Jupyter-based) |
| **Data Formats** | Excel `.xlsx`, CSV `.csv` |

---

## 📂 Dataset & Data Pipeline

### Source Files

| File | Description |
|------|-------------|
| `Quantium data.xlsx` | Transaction-level purchase records |
| `QVI_purchase_behaviour.csv` | Customer loyalty card segmentation data |
| `QVI_data.csv` | Final enriched dataset (merged output) |

### Processing Steps

**1. Data Cleaning**
- Removed duplicate transaction records
- Filtered out non-retail / bulk-buy outliers (e.g., transactions where `PROD_QTY = 200`)

**2. Data Formatting**
- Converted the `DATE` column from Excel serial number format to a standard Python `datetime` object

**3. Feature Engineering**
- Extracted **brand names** and **pack sizes** directly from the `PROD_NAME` column using string parsing

**4. Dataset Merging**
- Joined cleaned transaction data with customer loyalty data on `LYLTY_CARD_NBR` (loyalty card number)

---

## Task 1 — Customer & Purchasing Behavior Analysis

### Category-Level Summary

| Metric | Value |
|--------|-------|
| **Total FY 2018–19 Revenue** | $1,933,109 |
| **Total Transactions** | 264,833 |
| **Peak Sales Month** | January 2019 |
| **Notable Dips** | End of August 2018 & June 2019 |
| **Dominant Pack Size** | 175g (category anchor) |
| **Dominant Brand** | Kettle (leading across all segments) |

---

### Customer Segment Insights

#### Volume Drivers
- **Older Families — Budget & Mainstream tiers** generated the highest total sales revenue and transaction volumes, making them the backbone of category performance.

#### Value Drivers
- **Young Families** demonstrated strong loyalty with the **highest average annual spend per customer at $34.69**, indicating a high-value, retention-worthy segment.

#### Segment Size
- **Mainstream customers** represent **40.3% of the entire customer base** (29,245 customers) — the largest single tier.

#### Segment Extremes

| Segment | Metric | Value |
|---------|--------|-------|
| Mainstream Young Singles/Couples | Highest avg. transaction value | $7.56 |
| Budget Young Singles/Couples | Lowest avg. annual spend | $16.18 |

---

## Task 2 — Trial Store Performance Evaluation

### Trial Setup

- **Trial Period:** February – April 2019 (3 months)
- **Trial Stores:** 77, 86, 88
- **Matched Control Stores:** 233, 155, 237 respectively
- **Matching Method:** Stores were paired based on highly correlated pre-trial performance metrics (sales, customer count, transaction volume)

### Results Summary

All three trial stores **outperformed** their matched control stores across all key metrics during the trial window.

| Trial Store | Control Store | Sales Uplift | Unique Customer Uplift |
|-------------|---------------|--------------|------------------------|
| **Store 77** ⭐ | Store 233 | **+29.13%** | **+23.48%** |
| Store 86 | Store 155 | Positive | Positive |
| Store 88 | Store 237 | Positive | Positive |

> ⭐ **Store 77** was the top performer across all metrics.

### Statistical Caveat

While all trial stores showed **directionally strong positive results**, the **3-month observation window was too short** to reach formal statistical significance.

```
p-value > 0.05  →  Results do not meet the significance threshold
```

This does not mean the layout failed — it means the data collected is **not yet sufficient** to rule out random variation with confidence.

---

## 💡 Strategic Recommendations

### 1. Promotions — Target Volume Drivers
> Prioritize **Older Families (Budget & Mainstream)** for volume-based promotions. These customers are the primary revenue engine of the chips category.

### 2. Retention — Protect High-Value Segments
> Invest in **loyalty and retention strategies for Young Families**. Their high per-customer annual spend ($34.69) makes them disproportionately valuable relative to their segment size.

### 3. Inventory — Stock for Demand
> Ensure **175g pack sizes** are prominently displayed and that **Kettle brand** availability is maintained across all stores, as these drive consistent purchases across all customer segments.

### 4. Store Layout Rollout — Proceed with Caution
> The trial layout showed **strong directional uplift** (up to +29.13% in sales for Store 77), but the **3-month window was insufficient** to confirm statistical significance (`p > 0.05`).

**Recommended Action:**
- ✅ Proceed with a **cautious, monitored rollout**
- 📅 Extend the observation period to **6+ months** before committing to full network rollout
- 📊 Re-evaluate significance with the expanded data window

---

## 🗂️ Project Structure

```
quantium-retail-analytics/
│
├── data/
│   ├── Quantium data.xlsx          # Raw transaction data
│   ├── QVI_purchase_behaviour.csv  # Customer loyalty segmentation
│   └── QVI_data.csv                # Final merged & enriched dataset
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

## 📊 Key Visualizations

| Visual | Description |
|--------|-------------|
| Sales Trend Chart | Monthly revenue across FY 2018–19 highlighting peaks and dips |
| Customer Segment Revenue | Total revenue and transaction volume broken down by life stage and premium tier |
| Trial vs Control Comparison | Side-by-side performance of trial stores vs matched controls |

---

*This project was completed as part of the Quantium Data Analytics Virtual Experience Program.*
