# 🛒 Quantium Data Analytics Virtual Internship

## 📌 Project Overview
This project analyzes **264,833 chip transactions** across FY 2018–19 to evaluate the effectiveness of new trial store layouts and identify high-value customer purchasing behaviors. The goal is to determine whether the new store strategy drove enough sales uplift to justify a full network rollout.
**Top Result:** Trial Store 77 delivered a **+29.1% sales increase** and a **+23.5% boost in new customers**, providing strong directional evidence for the new layout's success.

---

## 🎯 Objectives
* Analyze transaction and customer data to identify volume drivers.
* Identify key customer segments (e.g., Older Families vs. Young Families).
* Evaluate trial store performance (Stores 77, 86, 88) versus matched control stores.
* Provide data-driven business recommendations regarding a full network rollout.

---

## 📊 Dataset
The dataset includes:
- **Transaction data** (`Quantium data.xlsx`): Sales, product details, transaction dates, and store numbers. 
- **Customer data** (`QVI_purchase_behaviour.csv`): Customer demographics and loyalty card segmentation. 
- **Enriched data** (`QVI_data.csv`): Final merged dataset connecting transaction records to specific customer tiers.

---

## ⚙️ Methodology
1. **Data Cleaning & Formatting**
   - Removed duplicates and filtered out bulk-buy outliers (e.g., `PROD_QTY = 200`). 
   - Converted Excel serial number dates into proper Python `datetime` objects for accurate time series analysis. 

2. **Feature Engineering & Merging**
   - Extracted brand names and pack sizes from product name strings to enable segment-level preference tracking.
   - Joined transaction and loyalty data on `LYLTY_CARD_NBR` to connect purchasing behavior to customer segments.

3. **Exploratory Data Analysis (EDA)**
   - Analyzed category-level sales trends across FY 2018–19. 
   - Examined customer purchasing patterns to identify high-value segments based on total revenue and average spend. 

4. **Trial vs Control Store Analysis**
   - Selected comparable control stores (233, 155, 237) matched to trial stores on pre-trial sales, customer count, and transaction volume. 
   - Compared performance before and after the 3-month trial (Feb–Apr 2019) using an Independent samples t-test. 

---

## 📈 Key Insights

### 1. The New Layout Drives Acquisition, Not Just Basket Size
Trial stores outperformed controls. Trial Store 77 was the standout, delivering a **+29.1% sales uplift** and a **+23.5% increase in unique customers** compared to its control store. This indicates the layout successfully brings in *new* chip buyers.

![Sales Trend Trial vs Control](images/task2_chart_6.png)
*(Note: Ensure this path matches where you save task2_chart_6.png)*

### 2. Volume vs. Value Segments
* **Older Families (Budget & Mainstream)** are the category's volume engine. They generate the most transactions, meaning any promotions here move the overall category numbers.
* **Young Families** hold the highest value per head (**$34.69/year**). Losing even a small percentage of these shoppers results in disproportionate revenue drops.

![Total Sales by Segment](images/task1_chart_3.png)
*(Note: Ensure this path matches where you save task1_chart_3.png)*

### 3. Single-SKU Revenue Risk
The **175g** pack size is the undeniable anchor, dominating every single customer segment. Stockouts on this specific item size present the single largest risk to daily revenue.

![Sales by Pack Size](images/task1_chart_5.png)
*(Note: Ensure this path matches where you save task1_chart_5.png)*

---

## 💡 Business Recommendations
* **Extend Trial Before Full Rollout:** While the 3-month trial results are highly positive, the data window is too short to reach formal statistical significance (p-value > 0.05). **Decision:** Keep the layout in the trial stores, but extend the observation window to 6+ months before committing capital to a network-wide rollout.
* **Automate Replenishment for 175g Packs:** Set strict minimum stock thresholds and automated alerts for the 175g size across all stores to eliminate out-of-stock revenue leakage.
* **Implement Targeted Segment Strategies:** * *To drive volume:* Launch multi-buy promotions (e.g., "2 for $X") targeted at Older Families. 
  * *To protect value:* Introduce a targeted retention mechanic (e.g., points multipliers or exclusive offers) for Young Families, as retention here is much cheaper than acquisition.

---

## 📌 Conclusion
The analysis strongly indicates that the new store layout improves both overall sales and new customer engagement. By committing to a statistically backed, phased rollout of the layout—combined with targeted inventory safeguards for top-selling SKUs and segment-specific promotions—the business is well-positioned to significantly maximize category revenue.
