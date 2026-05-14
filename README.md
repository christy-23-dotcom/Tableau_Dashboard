# 📊 Telecom Customer Churn Analysis

**Submitted By:** Christy Susan Philip  
**Tools Used:** Tableau, Excel  
**Date:** 02/20/2026  

---

## 🔎 Introduction
Customer churn is a major challenge in the telecom industry because acquiring new customers costs more than retaining existing ones.  
This project analyzes customer behavior patterns to identify key factors influencing churn and provides proactive retention strategies.

---

## 🎯 Objectives
- Identify key drivers of customer churn  
- Analyze customer segments with high churn risk  
- Provide actionable insights to reduce churn  
- Support data-driven decision making  

---

## 📂 Dataset
- Source: [Kaggle Telco Customer Churn Dataset](https://www.kaggle.com/datasets/mustafaoz158/telco-customer-churn)  
- Data fields: demographics, service usage, billing details, churn label  

---

## 🛠️ Technical Workflow

### 1. Data Cleaning
- Removed blanks from **Monthly Charges** field  
- Verified numeric fields (charges must be valid numbers)  
- Checked **Churn Label** values (`Yes` or `No`)  
- Kept `NULL` values in **Churn Reason** → important to track customers who stayed  
- Ensured no duplicate customer IDs  

### 2. Calculated Fields in Tableau
- **Churn Flag**  
    IF [Churn Label] = "Yes" THEN 1 ELSE 0 END
    Converts churn labels into numeric values for easier KPI calculation

- **Active Customers    
    COUNT([CustomerID]) - COUNT([Churn Flag])
    Measures customers who remain active

- **Churn Rate
    (SUM([Churn Flag]) / COUNT([CustomerID])) * 100
    Percentage of churned customers

### 3. Segmentation Fields
    Contract Type (Month-to-month, One year, Two year)
    Tenure bins (0–12 months, lifecycle ranges)
    Monthly Charges buckets (low, medium, high)
    Internet Service Type (Fiber optic, DSL, No internet)
    Payment Method categories (Electronic check, mailed check, bank transfer, credit card)
    Demographics (Gender, Senior Citizen)    

## 4. Dashboard Overview

The Telecom Customer Churn dashboard was designed to highlight KPIs and segment customers across multiple dimensions.  

### KPIs
- **Total Customers** → Count of unique customer IDs  
- **Total Churned** → Customers where Churn Label = Yes  
- **Active Customers** → Total Customers − Total Churned  
- **Churn Rate** → (Total Churned / Total Customers) × 100  

### Segmentation Criteria
- **Contract Type Analysis**  
  - Groups: Month-to-month, One year, Two year  
  - Metric: Average churn flag  
  - Purpose: Evaluate impact of contract commitment on churn  

- **Tenure Analysis**  
  - Grouped into monthly bins (0–12 range)  
  - Metric: Average churn rate  
  - Purpose: Identify lifecycle-based churn risk  

- **Monthly Charges Analysis**  
  - Charges bucketed into ranges  
  - Metric: Average churn flag  
  - Purpose: Assess price sensitivity  

- **Internet Service Type**  
  - Categories: Fiber optic, DSL, No internet  
  - Metric: Average churn rate  
  - Purpose: Compare churn across service types  

- **Payment Method**  
  - Categories: Electronic check, Mailed check, Bank transfer, Credit card  
  - Metric: Average churn rate  
  - Purpose: Identify payment behavior patterns  

- **Customer Reason (Bubble Chart)**  
  - Grouped by churn reason  
  - Bubble size: % of churned customers  
  - Purpose: Highlight primary churn drivers  

- **Demographics (Gender & Senior Citizen)**  
  - Segmented by demographic categories  
  - Metric: Average churn rate  
  - Purpose: Evaluate demographic influence on churn  

## 5. Key Insights

- Month-to-month contract customers show the **highest churn risk**.  
- Customers paying via **Electronic Check** have the highest churn rate compared to other payment methods.  
- **Fiber optic service users** churn more than DSL customers.  
- **High monthly charges** (upper ranges) → churn spikes significantly.  
- **Tenure effect**: customers who survive the first year are more likely to stay long term.  
- **Gender churn rate** is nearly identical (~26%), indicating gender is not a strong predictor.  
- **Senior citizens** show distinct churn patterns compared to non-senior customers.  
- Customer-reported churn reasons highlight:
  - Competitor offers  
  - Customer support experience (attitude of service personnel)  
  - Device-related concerns  

## 6. Business Recommendations

1. **Improve onboarding** for new customers (0–12 months) to reduce early churn.  
2. **Encourage long-term contracts** with discounts and loyalty perks.  
3. **Promote automatic payment methods** (bank transfer, credit card) instead of electronic checks.  
4. **Investigate fiber optic service quality** issues and address customer complaints.  
5. **Reward loyal customers** with recognition programs, perks, or exclusive offers.  
6. **Establish service quality monitoring** through regular call audits and customer feedback reviews.  


## 📸 Dashboard Screenshot

![Telco Customer Churn Dashboard](Telco%20Customer%20Churn%20Analysis%20Dashboard.png)


