# Customer Value Analysis (RFM & Logistic Regression)

## Project Overview
This project analyzes customer transaction behavior using RFM (Recency, Frequency, Monetary) analysis combined with a logistic regression model.

The objective is to identify high-value customers, understand revenue distribution across customer segments, and build a predictive model to support data-driven marketing and retention strategies.

---

## Dataset
This project uses the Online Retail dataset containing transactional data from a UK-based retail company.

Dataset source: https://www.kaggle.com/datasets/lakshmi25npathi/online-retail-dataset

The dataset includes invoice-level transaction data such as product details, quantity, unit price, customer ID, and invoice date. It is commonly used for customer segmentation and retail analytics.

---

## Tools Used
- Python  
- Google Colab  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Scikit-learn  

---

## Methodology
This project follows a structured analytics workflow:

- Business Understanding  
- Data Cleaning & Preparation  
- Exploratory Data Analysis  
- RFM (Recency, Frequency, Monetary) Analysis  
- Customer Segmentation  
- Logistic Regression Modeling  
- Model Interpretation  
- Business Recommendations  

---

## SQL Logic Example
The following SQL logic represents how customer revenue is calculated in a relational database:

```sql
SELECT CustomerID,
       SUM(Quantity * UnitPrice) AS Revenue
FROM online_retail
GROUP BY CustomerID;

---

## Key Findings
- High-value customers contribute a disproportionate share of total revenue.
- Monetary value is the strongest predictor of customer value.
- Customer behavior can be effectively segmented using RFM analysis.
- Predictive modeling helps identify valuable customers early.

---

## Business Recommendations
- Focus retention strategies on high-value customers to maximize revenue protection.
- Develop upselling strategies for mid-value customers to increase lifetime value.
- Run cost-efficient reactivation campaigns for low-value customers.
- Use predictive models to proactively target potential high-value customers.

---

## Results

The analysis successfully segments customers into value groups and builds a logistic regression model to predict high-value customers.

The model shows that monetary contribution is the most important factor in determining customer value, followed by frequency and recency.

---

## Notebook

Google Colab Notebook: (https://colab.research.google.com/drive/14EapA2vyTeJnMQtEw4exe2bffuW10ub1?usp=sharing)
