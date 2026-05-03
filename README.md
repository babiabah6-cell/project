# 📊 E-Commerce Growth & Logistics Strategy: Olist RFM Analysis

> **Transforming raw transactional data into actionable customer retention and operational strategies.**

## 📋 Executive Summary
This project provides a 360-degree performance overview of a Brazilian E-Commerce ecosystem (Olist). By integrating **RFM Customer Segmentation** with **Logistics Performance metrics**, I identified high-value customer clusters and operational bottlenecks that directly impact revenue and brand loyalty.

---

## 🚀 Key Business Impact
*   **Identified $10M+ in "At-Risk" Revenue:** Pinpointed high-value customers who haven't purchased recently, providing a clear target for automated win-back campaigns.
*   **Correlated Logistics to Brand Equity:** Data-driven proof that delayed orders result in a **~40% drop** in average customer review scores.
*   **Segmented 96K+ Customers:** Successfully categorized a massive user base (dominated by one-time buyers) into actionable groups like "Potential Loyalists" and "Champions."

---

## 🛠 Tech Stack & Skills
*   **Tool:** Power BI Desktop (utilizing the .pbip Project format for version control)
*   **Data Source:** [Olist Brazilian E-Commerce Dataset](https://kaggle.com)
*   **Languages:** DAX (Advanced Measures), Power Query / M (ETL & Data Transformation)
*   **Techniques:** RFM Modeling, Star Schema Data Modeling, Trend Analysis, Geospatial Mapping.

---

## 🔍 Deep Dive: The Three Pillars of Analysis

### 1. Customer Intelligence (RFM)
Built a dynamic segmentation model using Recency, Frequency, and Monetary scores (1-5).
*   **Champions:** High-frequency, high-spend customers. **Strategy:** Reward with exclusive early access.
*   **At-Risk:** High-value customers who have stopped buying. **Strategy:** Immediate personalized discount incentives.
*   **New Customers:** High-recency first-time buyers. **Strategy:** Tailored onboarding to drive a second purchase.

### 2. Logistics & Operational Efficiency
*   **Finding:** Average delivery time is 11.7 days.
*   **The "Delay Gap":** Identified that the 7% of orders experiencing delays suffer a critical drop in satisfaction (Avg Review 3.4).
*   **Geospatial Insights:** Visualized delivery inefficiencies by state to identify regions requiring courier partnership optimization.

### 3. Executive Sales Overview
*   **Revenue Trend:** Monitored $41.5M in total revenue, identifying key seasonal growth peaks.
*   **Logistics Health:** Implemented real-time tracking for `% Delayed Orders` to maintain operational standards.

---

## 📐 Data Architecture (DAX Highlight)
To handle the unique "Olist Reality" (high volume of one-time buyers), I implemented a priority-based segmentation logic:

```dax
Customer_Segment = 
SWITCH( TRUE(),
    R >= 4 && F >= 4 && M >= 4, "Champions",
    R = 1 && F >= 4, "Can't Lose Them",
    R >= 4 && F = 1, "New Customers",
    "Need Attention"
)
```

---

## ⏭️ Future Roadmap
1. **Cloud Automation:** Migrating the ETL process to **Google BigQuery** for automated, scheduled data refreshes.
2. **Predictive Analytics:** Integrating Python-based churn prediction models directly into the Power BI environment.

---

