# 💎 Customer Value Analysis – RFM & Logistic Regression

> **Who Are Your Best Customers? Segment, Predict, and Retain with Data**  
> Combining RFM analysis and machine learning to identify high-value customers and drive revenue growth.

![Python](https://img.shields.io/badge/Python-3.10-blue.svg)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.3-F7931E?logo=scikit-learn)
![Google Colab](https://img.shields.io/badge/Run%20on-Google%20Colab-F9AB00?logo=googlecolab)
![Dataset](https://img.shields.io/badge/Dataset-Kaggle-20BEFF?logo=kaggle)

## 🎯 Project Overview

Not all customers are created equal. This project analyzes **Online Retail transaction data** using **RFM Analysis** and **Logistic Regression** to answer two critical business questions:

1. **Which customers drive the most revenue?**
2. **Can we predict high-value customers before they spend big?**

The goal: segment customers by value and build a predictive model to support targeted marketing, retention, and upselling strategies.

## 📂 Dataset

**Source**: [Kaggle – Online Retail Dataset](https://www.kaggle.com/datasets/lakshmi25npathi/online-retail-dataset)

UK-based online retail transactions from 2010–2011. Contains invoice-level data including `InvoiceNo`, `StockCode`, `Quantity`, `UnitPrice`, `CustomerID`, and `InvoiceDate`.

**Why this dataset?** Perfect for customer segmentation, RFM modeling, and retail analytics. It's the industry standard for learning customer lifetime value analysis.

## 🛠️ Tech Stack

| Tool | Purpose |
| --- | --- |
| **Python** | Core programming language |
| **Pandas & NumPy** | Data cleaning, RFM calculation, feature engineering |
| **Scikit-learn** | Logistic Regression modeling & evaluation |
| **Matplotlib & Seaborn** | Customer segment visualization |
| **Google Colab** | Cloud-based notebook environment |

## 🔬 Methodology

End-to-end analytics workflow following data science best practices:

1. **Business Understanding** → Define customer value problem
2. **Data Cleaning & Preparation** → Handle returns, missing `CustomerID`, outliers
3. **Exploratory Data Analysis** → Understand transaction patterns
4. **RFM Analysis** → Calculate Recency, Frequency, Monetary scores for each customer
5. **Customer Segmentation** → Group customers into High, Mid, Low value tiers
6. **Logistic Regression Modeling** → Predict probability of being a high-value customer
7. **Model Interpretation** → Identify key drivers using coefficients/feature importance
8. **Business Recommendations** → Translate model output into marketing actions

## 🔍 Key Findings

The analysis revealed the **Pareto Principle** in action:

1. **Revenue Concentration** → High-value customers contribute a **disproportionate share** of total revenue. Small group, big impact.
2. **Monetary Rules** → `Monetary` value is the **strongest predictor** of customer value, followed by `Frequency`, then `Recency`.
3. **RFM Works** → Customer behavior can be effectively segmented using RFM. The scores create clear, actionable groups.
4. **Prediction is Possible** → Logistic Regression successfully identifies potential high-value customers early in their lifecycle.

## 💡 Business Recommendations

Turn insights into revenue with these 4 strategies:

1. **Protect Your VIPs** → Focus premium retention campaigns on high-value customers. They're your revenue engine.
2. **Upsell the Middle Tier** → Develop targeted offers for mid-value customers to increase their frequency and monetary value.
3. **Reactivate at Low Cost** → Run efficient, automated email campaigns for low-value customers. Don't overspend here.
4. **Predict & Target Early** → Use the logistic regression model to flag new customers who show high-value potential and nurture them from day one.

## 📈 Results

- Successfully segmented 4,000+ customers into 3 distinct value groups using RFM scoring.
- Built a Logistic Regression model to predict high-value customers with clear feature interpretability.
- Model confirms business intuition: **Monetary contribution > Frequency > Recency** in determining customer value.

## 🗄️ SQL Logic Example

This SQL represents how core RFM metrics like customer revenue are calculated in a relational database environment:

```sql
-- Calculate total revenue per customer
SELECT 
    CustomerID,
    SUM(Quantity * UnitPrice) AS Revenue
FROM online_retail
GROUP BY CustomerID;

-- Rank customers by revenue for business prioritization
SELECT 
    CustomerID,
    SUM(Quantity * UnitPrice) AS Revenue,
    RANK() OVER (ORDER BY SUM(Quantity * UnitPrice) DESC) AS revenue_rank
FROM online_retail
GROUP BY CustomerID;

-- Segment customers into 3 tiers using NTILE (quantile-style)
SELECT *,
       NTILE(3) OVER (ORDER BY Revenue DESC) AS revenue_segment
FROM (
    SELECT CustomerID,
           SUM(Quantity * UnitPrice) AS Revenue
    FROM online_retail
    GROUP BY CustomerID
) t;
```

## 🚀 Run the Analysis

See the full RFM calculation, segmentation, and model code:

**▶️ Open in Google Colab**: [Customer Value Analysis Notebook](https://colab.research.google.com/drive/14EapA2vyTeJnMQtEw4exe2bffuW10ub1?usp=sharing)

---

**Project Type**: Data Analyst / Data Science Portfolio Project  
**Focus**: Customer Segmentation, RFM Analysis, Predictive Modeling, Retail Analytics
