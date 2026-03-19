
## 📌 Project Overview
This portfolio project focuses on two primary objectives for a major Australian supermarket chain: 
* **Task 1: Customer & Purchasing Behavior Analysis** 
* **Task 2: Trial Store Performance Evaluation** 

The goal was to understand which customer segments drive sales volume and value, identify product preferences, and evaluate if a new in-store layout intervention was successful enough to roll out across the broader store network.

---

## 🛠️ Tools & Technologies
* **Language:** Python 3 
* **Libraries:** pandas, NumPy, Matplotlib, SciPy (t-test for trial significance) 
***Environment:** Kaggle Notebooks (Jupyter-based) 
* **Data Formats:** Excel (.xlsx), CSV (.csv) 

---

## 📂 Dataset & Methodology
The analysis utilized transaction-level data (`Quantium data.xlsx`) and customer loyalty card data (`QVI_purchase_behaviour.csv`), which were later combined into an enriched dataset (`QVI_data.csv`) covering the FY 2018–19 period.

**Data Processing Steps:**
 **Cleaning:** Removed duplicate records and filtered out non-retail/bulk outliers (e.g., transactions where `PROD_QTY = 200`)
**Formatting:** Converted the `DATE` column from an Excel serial number to a standard Python datetime format.
 **Feature Engineering:** Extracted brand names and pack sizes directly from the `PROD_NAME` column using string parsing.
**Merging:** Joined the cleaned transaction and customer datasets using the loyalty card number (`LYLTY_CARD_NBR`).

---

##  Customer Behavior & Category Insights

### Category Overview
**Total FY 2018–19 Revenue:** $1,933,109 across 264,833 transactions
**Sales Trends:** Peak sales occurred in January 2019, with noticeable dips at the end of August 2018 and June 2019.
**Product Preferences:** The 175g pack size is the category anchor, and Kettle is the dominant brand across all customer segments

*(Upload your Sales Trends chart here and update the path)*
`![Sales Trends](images/sales_trends.png)`

### Customer Segments
**Volume Drivers:** Older Families in the Budget and Mainstream tiers generated the highest total sales revenue and transaction volumes.
**Value Drivers:** Young Families showed strong loyalty and larger basket sizes, boasting the highest average annual spend per customer at $34.69.
* **Segment Sizes:** Mainstream tier customers represent 40.3% of the entire customer base (29,245 customers).
**Extremes:** Mainstream Young Singles/Couples had the highest average transaction value ($7.56), while Budget Young Singles/Couples were the lowest-value segment ($16.18 average annual spend).

*(Upload your Customer Segments chart here and update the path)*
`![Customer Segments](images/customer_segments.png)`

---

## 🏬 Task 2: Trial Store Performance

A new store layout was trialed from February to April 2019.Trial stores were matched with control stores based on highly correlated pre-trial performance metrics.

**Results:**
* All three trial stores (77, 86, and 88) outperformed their matched control stores (233, 155, and 237) in Total Sales, Customer Count, and Transaction Volume during the trial window.
* [cite_start]**Store 77 (Top Performer):** Delivered a +29.13% increase in total sales and a +23.48% increase in unique customers compared to its control store.

*(Upload your Trial Store Performance chart here and update the path)*
`![Trial Store Performance](images/trial_performance.png)`

---

## 💡 Strategic Recommendations
1. **Promotions:** Prioritize Older Families (Budget & Mainstream) for volume-based promotions, as they are the backbone of category revenue.
2. **Retention:** Invest in retention strategies for Young Families to protect their high per-customer spend.
3. **Inventory:** Stock the 175g pack size prominently and ensure Kettle brand availability across all stores.
4. **Layout Rollout:** While the trial layout showed directionally positive results, the short three-month window meant results did not reach statistical significance ($p > 0.05$).A cautious, monitored rollout is recommended, extending the observation period to 6+ months before committing to a full network rollout.

## 💡 Recommendations & Next Steps
* **Rollout Strategy:** Proceed with a cautious, monitored rollout of the new store layouts. 
* **Statistical Caveat:** Because of the short three-month trial window, the strong percentage uplifts for Store 77 did not achieve formal statistical significance (p > 0.05). 
* **Monitoring:** It is highly recommended to extend the monitoring period before executing a full network-wide rollout to ensure long-term sustained growth.
