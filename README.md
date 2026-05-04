# 📊 E-Commerce Growth & Logistics Strategy: Olist RFM Analysis

> **Transforming 100k+ raw records into actionable retention and nearshoring strategies using Python and Power BI.**

## 📋 Executive Summary
This project provides a 360-degree performance overview of a Brazilian E-Commerce ecosystem (Olist). By engineering an end-to-end **Python data pipeline** and integrating **RFM Customer Segmentation** with logistics metrics, I identified high-value customer clusters and operational bottlenecks critical for supply chain regionalization.

---

## 🚀 Key Business Impact
*   **Identified $10M+ in "At-Risk" Revenue:** Pinpointed high-value customers who haven't purchased recently, providing a clear target for automated win-back campaigns.
*   **Correlated Logistics to Brand Equity:** Data-driven proof that delayed orders result in a **~40% drop** in average customer review scores.
*   **Nearshoring Intelligence:** Mapped state-level delivery inefficiencies to identify regions where **regional fulfillment hubs** (nearshoring) would most effectively reduce the 7.08% delay rate.
*   **Segmented 96K+ Customers:** Categorized a massive user base into actionable groups like "Potential Loyalists" and "Champions."

---

## 🛠 Tech Stack & Skills
*   **Data Engineering:** **Python (Pandas, NumPy)** for ETL, handling 9 relational tables, and multi-step data cleaning.
*   **Visualization:** Power BI Desktop (utilizing the **.pbip** Project format for professional version control).
*   **Analytics:** RFM Modeling, Star Schema Data Modeling, Trend Analysis, Geospatial Mapping.
*   **Environment:** Jupyter Notebooks for Exploratory Data Analysis (EDA).

---

## 🔍 Deep Dive: The Three Pillars of Analysis

### 1. Customer Intelligence (RFM)
Built a dynamic segmentation model using **Python** to calculate Recency, Frequency, and Monetary scores.

*   **Champions:** High-frequency, high-spend customers. **Strategy:** Reward with exclusive early access.
*   **At-Risk:** High-value customers who have stopped buying. **Strategy:** Immediate personalized discount incentives.

### 2. Logistics & Nearshoring Feasibility
*   **The "Delay Gap":** Identified that orders exceeding the 11.7-day delivery average suffer a critical drop in satisfaction (Avg Review 3.4).
*   **Geospatial Insights:** Analyzed delivery times by state to identify where logistics infrastructure requires optimization—a key metric for **nearshoring** and regional hub planning.

### 3. Executive Sales Overview
*   **Revenue Trend:** Monitored $41.5M in total revenue, identifying key seasonal growth peaks.
*   **Performance Tracking:** Implemented real-time tracking for `% Delayed Orders` to maintain operational standards.

---

## 📐 Technical Implementation (Python ETL)
To handle the 9-table relational structure, I developed a Python-based pipeline for more complex transformations than standard SQL allows:

```python
import pandas as pd

# Engineering RFM Metrics
snapshot_date = df_full['order_purchase_timestamp'].max() + pd.Timedelta(days=1)

rfm = df_full.groupby('customer_unique_id').agg({
    'order_purchase_timestamp': lambda x: (snapshot_date - x.max()).days,
    'order_id': 'nunique',
    'payment_value': 'sum'
}).rename(columns={'order_purchase_timestamp': 'Recency', 
                   'order_id': 'Frequency', 
                   'payment_value': 'Monetary'})

# Dynamic Scoring Logic (Assigning segments 1-5)
rfm['R_Score'] = pd.qcut(rfm['Recency'], 5, labels=[5,4,3,2,1])
rfm['F_Score'] = pd.qcut(rfm['Frequency'].rank(method="first"), 5, labels=[1,2,3,4,5])
```

---

## ⏭️ Future Roadmap
1. **Predictive Analytics:** Integrating `Scikit-learn` to build a churn prediction model.
2. **Cloud Automation:** Moving the Python ETL to a cloud function for automated, scheduled data refreshes.

---
**Author:** [Your Name]  
**Connect with me on [LinkedIn](Your-LinkedIn-URL)**
