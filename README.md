# food-delivery-analytics-dashboard
Interactive Power BI dashboard analyzing food delivery operations, customer behavior, restaurant performance, and business insights using DAX, Power Query, and data visualization.

# 🚀 Food Delivery Analytics Dashboard | Power BI

An interactive Power BI Analytics Project built using real-world Kaggle food delivery data to analyze customer behavior, restaurant performance, delivery operations, and business insights using Excel, Power BI, Power Query, DAX, and data visualization.

---

# 📌 Dashboard Pages

## 1️⃣ Executive Overviews

High-level business KPIs and overall performance insights.

### Key Metrics:
- Total Revenue
- Total Orders
- Avg Order Value
- Avg Delivery Time
- Revenue Trends
- Orders Trends

<img width="1612" height="892" alt="{22926185-3900-43E7-8BE5-01667A802A4E}" src="https://github.com/user-attachments/assets/5b686b72-ffa2-4e42-8472-ecda89f07f73" />

## 2️⃣ Customer Analytics

Customer segmentation and behavioral analysis.

### Key Insights:
- Repeat Customers
- Customer Retention
- Orders Per Customer
- New vs Returning Customers
- Signup Trends

<img width="1598" height="889" alt="{627AE81F-99E4-4AD1-8273-7DF644E6F6F8}" src="https://github.com/user-attachments/assets/23a8d598-9bca-4742-aa5c-4c0610f56cbd" />

---

## 3️⃣ Restaurant Performance

Performance analysis of restaurants and cuisines.

### Key Insights:
- Top Restaurants
- Revenue by Restaurant
- Cuisine Analysis
- Rating Analysis
- Cost Bucket Analysis

<img width="1588" height="893" alt="{B7C5E355-4061-445A-9408-3B509DE0DF31}" src="https://github.com/user-attachments/assets/385bcf8e-f564-4ed9-87f3-a06a039bdc55" />

---

## 4️⃣ Delivery And Operations

Operational efficiency and delivery performance tracking.

### Key Insights:
- Late Deliveries
- Cancellation Analysis
- Delivery Time Trends
- City-wise Delivery Performance

<img width="1603" height="885" alt="{B9628358-7B79-4A6C-BFD6-B5578FCBB5E2}" src="https://github.com/user-attachments/assets/82559ba3-dc85-412e-aa63-4d29822b443c" />

---

## 5️⃣ Restaurant Details

Detailed restaurant-level operational and revenue insights.

### Key Insights:
- Restaurant KPIs
- Revenue Trends
- Orders Trends
- Customer Distribution
- Cuisine-wise Orders

<img width="1579" height="884" alt="{C02EEF00-6F91-456A-A468-3E03429A7BEE}" src="https://github.com/user-attachments/assets/711caa08-fba4-4bb6-8d01-6ff6718e75c8" />

---

## 6️⃣ Advanced Insights

Advanced KPI analysis and comparative business metrics.

### Key Insights:
- KPI Selector
- Revenue vs Rating vs Cost
- Dynamic Analysis
- Business Performance Comparison

<img width="1519" height="856" alt="{F7F43C9F-3702-4C54-91F5-D11D7612F95A}" src="https://github.com/user-attachments/assets/412ce11e-33de-41cf-9f43-99a050c4055c" />

---

# 🛠️ Tools & Technologies

- Excel
- Power BI
- Power Query
- DAX
- Data Modeling
- Data Visualization

---

# 📂 Data Source

- Real-world Food Delivery Dataset from Kaggle

---

# ⚙️ Project Workflow

```text
Import Dataset
Inspect Columns
Data Cleaning using Power Query
Create RestaurantID
Build Fact & Dimension Tables
Create Relationships
Create Calculated Columns
Create DAX Measures
Dashboard Development
Add Slicers & Interactions
Final Formatting
```

---

# 📌 Calculated Columns

## Restaurants Table

### Cost Bucket

```DAX
Cost Bucket =
SWITCH(
    TRUE(),
    Restaurants[CostForTwo] < 500, "Budget",
    Restaurants[CostForTwo] < 1000, "Mid Range",
    "Premium"
)
```

### Rating Bucket

```DAX
Rating Bucket =
SWITCH(
    TRUE(),
    Restaurants[Rating] >= 4.5, "Excellent",
    Restaurants[Rating] >= 4.0, "Good",
    Restaurants[Rating] >= 3.0, "Average",
    "Low"
)
```

---

## Orders Table

### Delivery Status

```DAX
Delivery Status =
IF(Orders[DeliveryTimeMins] > 45, "Late", "On Time")
```

### Order Month

```DAX
Order Month = FORMAT(Orders[OrderDate], "MMM YYYY")
```

---

# 📌 Core Measures

## KPI Measures

```DAX
Total Orders = COUNT(Orders[OrderID])

Total Revenue = SUM(Orders[OrderValue])

Avg Order Value = DIVIDE([Total Revenue], [Total Orders])

Avg Delivery Time = AVERAGE(Orders[DeliveryTimeMins])

Total Customers = DISTINCTCOUNT(Orders[CustomerID])

Total Restaurants = DISTINCTCOUNT(Restaurants[RestaurantID])
```

---

## Status Measures

```DAX
Delivered Orders =
CALCULATE([Total Orders], Orders[OrderStatus] = "Delivered")

Cancelled Orders =
CALCULATE([Total Orders], Orders[OrderStatus] = "Cancelled")

Cancellation % =
DIVIDE([Cancelled Orders], [Total Orders])

Late Orders =
CALCULATE([Total Orders], Orders[Delivery Status] = "Late")

Late Delivery % =
DIVIDE([Late Orders], [Total Orders])
```

---

## Customer Measures

```DAX
Repeat Customers =
COUNTROWS(
    FILTER(
        VALUES(Orders[CustomerID]),
        CALCULATE(COUNT(Orders[OrderID])) > 1
    )
)

Repeat Customer % =
DIVIDE([Repeat Customers], [Total Customers])

Orders Per Customer =
DIVIDE([Total Orders], [Total Customers])
```

---

## Restaurant Measures

```DAX
Revenue per Restaurant =
DIVIDE([Total Revenue], [Total Restaurants])

Avg Rating = AVERAGE(Restaurants[Rating])

Avg Votes = AVERAGE(Restaurants[Votes])
```

---

# 📈 Key Insights

- Identified high-performing restaurants and cuisines
- Analyzed customer retention and repeat behavior
- Evaluated delivery efficiency and late deliveries
- Tracked cancellation patterns across cities
- Compared revenue performance across cost categories

---

# 🚀 Business Impact

This dashboard helps businesses:
- Improve operational efficiency
- Optimize delivery performance
- Understand customer behavior
- Monitor restaurant growth
- Make data-driven business decisions

---

# 📌 Project Status

✅ Completed

---

# 🔗 Connect With Me

## LinkedIn
Add your LinkedIn profile link
