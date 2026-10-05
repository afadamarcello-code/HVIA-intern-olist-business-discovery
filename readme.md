# Olist E-Commerce Business Discovery & AI Solutions

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458.svg)](https://pandas.pydata.org/)
[![Domain](https://img.shields.io/badge/Domain-E--Commerce%20%26%20Logistics-orange.svg)]()

> **HVIA Data & AI Solutions Internship Trial Task**  
> A data consultancy project combining Python-driven Exploratory Data Analysis (EDA) with strategic business analysis to uncover operational friction points and propose practical AI solutions for Olist.

---

## 📊 Project Overview

| Attribute | Details |
| :--- | :--- |
| **Target Company** | **Olist** (Brazilian B2B E-Commerce & Merchant Integration Platform) |
| **Dataset** | Brazilian E-Commerce Public Dataset by Olist (~100k orders, 2016–2018) |
| **Objective** | Discover operational bottlenecks and propose business-aligned AI/ML systems |
| **Tech Stack** | Python, Pandas, NumPy, Jupyter Notebook, Data Visualization |

---

## 🏢 1. Company Research Summary

**Olist** is a Brazilian B2B retail technology company providing an integrated ecosystem for small and medium-sized enterprises (SMBs). By connecting merchants directly to major Brazilian marketplaces, Olist handles e-commerce store management, logistics coordination, payment collection, and seller credit services. 

* **Core Customers:** SMB sellers seeking online channel expansion without operational overhead.
* **Revenue Model:** Monthly subscription fees combined with commission rates on seller sales volume.
* **Strategic Objective:** Eliminate seller operational friction to maximize platform Gross Merchandise Value (GMV) and maintain end-consumer retention.

---

## 🗂️ 2. Dataset Understanding & Schema

Out of Olist's 8 relational tables, **5 core tables** tracking the primary order lifecycle were isolated for logistics and seller performance analysis:

* **`olist_orders_dataset` (Central Hub):** Links `customer_id` to `order_id` and tracks complete order status timestamps (purchase, approval, shipping, delivery).
* **`olist_order_items_dataset`:** Connects each order line item to its respective `product_id`, `seller_id`, item price, and split `freight_value`.
* **`olist_order_reviews_dataset`:** Stores post-delivery customer satisfaction ratings (1 to 5 stars) and qualitative text reviews.
* **`olist_customers_dataset` & `olist_sellers_dataset`:** Captures zip codes and geographic location data for route and distance mapping.

> *Note: Geolocation, payment sequence, and product translation tables were excluded as non-essential to core logistics and seller friction diagnostics.*

---

## 🔍 3. Key Findings & Business Impact

### 🚨 Finding 1: The Logistics Friction
Analyzing actual delivery dates (`order_delivered_customer_date`) against estimated dates (`order_estimated_delivery_date`) revealed a sharp, inverse relationship with customer satisfaction scores:

| Delivery Delay Status | Time Difference | Average Review Score |
| :--- | :--- | :--- |
| **On Time / Early** | <= 0 days delay | **4.28 / 5.0** |
| **Slightly Late** | 1 to 3 days delay | **3.28 / 5.0** |
| **Very Late** | > 3 days delay | **1.85 / 5.0** |

* **Business Impact:** Late deliveries severely damage marketplace reputation. Accumulating 1-star reviews leads to merchant suspensions on major channels, directly impacting Olist's commission revenue.

---

### ⚠️ Finding 2: Seller Revenue Concentration Risk
Analyzing Gross Merchandise Value (GMV) distribution across the merchant base revealed extreme revenue skewness:

* **Top Performers:** Out of 3,095 active sellers, **129 sellers (4.17%) account for 50% of total revenue**.
* **Underperformers:** The bottom 20% of sellers generated **less than $159.76** in total lifetime revenue.


```text
Seller Distribution:
[████ 4.17% ] -> 50% Total Sales (129 Sellers)
[░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░] -> Remaining 50%
```



🚀 How Data & AI Can Protect E-Commerce Revenue: Lessons from 100k Olist Orders

As part of a Data Strategy task with HVIA - Data & AI Solutions, I conducted a deep-dive analysis on Olist’s public Brazilian e-commerce dataset (100k+ orders). 

My goal wasn't just to analyze data, but to act as a Data Consultant—identifying core operational friction points and designing realistic, business-aligned AI solutions.

Here are the 2 major findings from the analysis:

1️⃣ The Cost of Late Deliveries 📦
• Orders delivered on time/early enjoy a 4.28/5 average review rating.
• Deliveries that are >3 days late crash to a 1.85/5 rating.
💡 Business Impact: Late shipping destroys seller ratings on major marketplaces, leading to seller suspensions and cutting directly into Olist's commission revenue.

2️⃣ Extreme Seller Concentration Risk 📊
• Out of 3,095 active sellers, just 129 merchants (4.17%) generate 50% of total revenue.
• The bottom 20% of sellers generated less than $160 in total sales.
💡 Business Impact: Massive revenue fragility. Losing a small fraction of top-tier sellers creates a huge financial shock, while inactive "zombie" sellers drain onboarding bandwidth.

💡 The Proposed HVIA AI Solutions:
To protect revenue and scale operations, I proposed a two-pronged Predictive Intelligence Suite:

1. Predictive Late-Delivery Alert System: A Machine Learning model predicting late-delivery risk at checkout based on seller history, distance, and freight data—allowing Olist to adjust delivery promises or expedite high-risk packages before bad reviews happen.
2. Predictive Seller Churn & Tiering Model: An automated monitoring system tracking seller health to trigger retention workflows for top earners and automate support for low-activity merchants.

🛠️ Tools Used: Python | Pandas | Exploratory Data Analysis | Data Strategy
