# 🛒 Quantium Data Analytics Virtual Internship

## 📌 Project Overview
This project evaluates a new store layout by analyzing **264,833 chip transactions** (FY 2018–19). By comparing trial stores (77, 86, 88) against matched controls, I quantified the layout’s impact on sales and customer acquisition to drive a data-backed national rollout strategy.

---

## 🎯 Objectives
* **Identify Drivers:** Pinpoint volume and value drivers through transaction and demographic analysis.
* **Segment Customers:** Profile key groups (e.g., Older vs. Young Families) to identify growth opportunities.
* **Quantify Performance:** Validate trial store performance using t-tests and matched-pair control stores.
* **Strategic Advice:** Deliver high-confidence recommendations for a network-wide execution.

---

## 📊 Dataset
* **Transaction Data** (`Quantium data.xlsx`): Sales, product details, and timestamps.
* **Customer data** (`QVI_purchase_behaviour.csv`): Demographics and loyalty segments.
* **Enriched data** (`QVI_data.csv`): Merged dataset connecting behavior to specific customer tiers.

---

## ⚙️ Methodology
1. **Data Cleaning:** Removed bulk-buy outliers (200+ units) and synchronized time-series data.
2. **Feature Engineering:** Segmented brand names and pack sizes; merged datasets on `LYLTY_CARD_NBR`.
3. **EDA:** Identified revenue anchors and high-frequency purchasing patterns across segments.
4. **Statistical Testing:** Conducted Independent samples t-tests comparing trial stores to controls (233, 155, 237) over a 3-month trial period.

---

## 📈 Key Insights

### 1. Proven Acquisition Uplift
The new layout is a significant driver of new foot traffic. **Trial Store 77** delivered a **29.1% sales increase** and a **23.5% surge in unique customers**. **Store 86** followed with an **11% sales lift** and **8% more customers**, confirming the layout attracts new buyers.

![Sales Trend Trial vs Control](https://github.com/user-attachments/assets/e8b6bf4b-5175-45d5-b002-855efffb192f)

### 2. High-Value vs. High-Volume Segments
* **Older Families (Mainstream/Budget):** The "Volume Engine," contributing over **25% of total category sales**. They are the primary target for frequency-based promotions.
* **Young Families:** The "Value Anchor," yielding the highest spend per capita at **$34.69/year**. A 5% churn in this segment represents a significantly higher revenue risk.

![Total Sales by Segment](https://github.com/user-attachments/assets/363e4fc9-784d-4388-bba4-46b05d0291b1)

### 3. Critical SKU Dependency
The **175g pack size** is the undisputed category leader. In Trial Store 77, this size accounted for nearly **30% of category revenue**. Any stockout in this specific SKU results in immediate revenue leakage.

![Sales by Pack Size](https://github.com/user-attachments/assets/363e4fc9-784d-4388-bba4-46b05d0291b1)

---

## 💡 Business Recommendations
* **Execute National Rollout:** Based on the consistent **29.1% uplift** in key trial sites, the layout is commercially viable. Proceed with a phased rollout, prioritizing high-traffic urban zones.
* **Mandate 175g Inventory Buffers:** Implement a **zero-out-of-stock policy** for all 175g SKUs. Automate replenishment triggers at 15% shelf capacity to eliminate revenue loss.
* **Deploy Segmented Loyalty Plays:** * **Volume Play:** Launch "Buy 3 for $X" deals for Older Families to capitalize on high transaction frequency.
    * **Retention Play:** Issue "Loyalty Multipliers" for Young Families to protect the high $34.69/year value-per-customer.

---

## 📌 Conclusion
The analysis confirms that the new layout successfully drives both top-line revenue and customer acquisition. By scaling this layout and securing the 175g supply chain, the business is positioned to maximize category growth in the upcoming fiscal year.
