# 🍔 Food Delivery Analytics Dashboard | Power BI

Interactive Power BI dashboard built using real-world food delivery data to analyze customer behavior, restaurant performance, delivery operations, and business KPIs using Power BI, Power Query, DAX, and advanced data visualization techniques.

---

# 📌 Project Overview

This project transforms raw food delivery data into actionable business insights through an interactive and visually rich Power BI dashboard.

The dashboard helps stakeholders:
- Monitor revenue and operational performance
- Analyze customer behavior and retention
- Evaluate restaurant and cuisine performance
- Track delivery efficiency and cancellations
- Support data-driven business decisions

---

 🚀 Live Interactive Dashboard

👉 [View Power BI Dashboard](https://app.powerbi.com/links/yfdxGwssm1?ctid=ad65900e-6f0f-4391-ac11-c968650c084c&pbi_source=linkShare&bookmarkGuid=783322a6-1b0f-4da8-a839-a44d0e443151)

# 🚀 Dashboard Pages

---

# 1️⃣ Executive Overview

Provides a high-level summary of business performance and operational KPIs.

## Key Insights
- Total Revenue Analysis
- Order Trends
- Revenue Trends
- City-wise Revenue Distribution
- Top Performing Restaurants
- Order Status Analysis

## KPIs
- Total Orders
- Total Revenue
- Average Order Value
- Average Delivery Time

## 📷 Dashboard Preview
<img width="1612" height="892" alt="{22926185-3900-43E7-8BE5-01667A802A4E}" src="https://github.com/user-attachments/assets/5b686b72-ffa2-4e42-8472-ecda89f07f73" />

---

# 2️⃣ Customer Analytics

Analyzes customer behavior, retention, and engagement trends.

## Key Insights
- Repeat Customer Analysis
- Customer Retention Tracking
- Orders Per Customer
- New vs Returning Customers
- Customer Signup Trends

## Business Value
- Identifies loyal customers
- Improves retention strategies
- Enhances customer engagement analysis

## 📷 Dashboard Preview
<img width="1598" height="889" alt="image" src="https://github.com/user-attachments/assets/210429cb-6587-409f-9a7d-f6733ebffcee" />

---

# 3️⃣ Restaurant Performance

Provides detailed insights into restaurant growth, cuisine popularity, and customer preferences.

## Key Insights
- Top Performing Restaurants
- Revenue by Restaurant
- Cuisine Analysis
- Rating Analysis
- Cost Bucket Analysis

## KPIs
- Total Restaurants
- Average Rating
- Average Votes
- Revenue per Restaurant

## Business Value
- Identifies high-performing cuisines
- Evaluates restaurant revenue contribution
- Supports partnership and pricing strategies

## 📷 Dashboard Preview
<img width="1588" height="893" alt="image" src="https://github.com/user-attachments/assets/84741706-ab5c-4a1a-afa0-1869e0314a0b" />

---

# 4️⃣ Delivery & Operations

Tracks operational efficiency and delivery performance.

## Key Insights
- Late Delivery Analysis
- Cancellation Tracking
- Delivery Time Trends
- City-wise Delivery Performance
- Customer Order Behavior

## KPIs
- Late Orders
- Cancelled Orders
- Average Delivery Time
- Late Delivery Percentage

## Business Value
- Improves delivery efficiency
- Reduces operational delays
- Optimizes logistics planning

## 📷 Dashboard Preview
<img width="1603" height="885" alt="image" src="https://github.com/user-attachments/assets/253b0984-5959-4ddf-bd8e-1d6b8c8889d1" />

---

# 5️⃣ Restaurant Details

Provides detailed restaurant-level operational and revenue analysis.

## Key Insights
- Revenue Trends
- Orders Trends
- Cuisine-wise Orders
- New vs Repeat Customers
- Restaurant KPI Monitoring

## Business Value
- Tracks restaurant growth
- Evaluates customer loyalty
- Supports menu optimization

## 📷 Dashboard Preview
<img width="1579" height="884" alt="image" src="https://github.com/user-attachments/assets/b9631de4-03bf-4711-ac7a-3563b84165c7" />

---

# 6️⃣ Advanced Insights

Advanced KPI comparison and dynamic business analysis dashboard.

## Key Insights
- Dynamic KPI Selection
- Revenue vs Rating vs Cost Analysis
- Comparative Business Metrics
- Trend Analysis

## Business Value
- Supports strategic decision-making
- Enables advanced business comparisons
- Enhances KPI monitoring

## 📷 Dashboard Preview
<img width="1519" height="856" alt="image" src="https://github.com/user-attachments/assets/1e53dee9-ba4f-4089-b1a5-ae523d61dca8" />

---

# 🛠️ Tools & Technologies Used

- Power BI
- Power Query
- DAX (Data Analysis Expressions)
- Microsoft Excel
- Data Modeling
- Data Visualization

---

# ⚙️ Project Workflow

```text
Data Collection
↓
Data Cleaning using Power Query
↓
Data Transformation
↓
Data Modeling
↓
Relationship Building
↓
Calculated Columns Creation
↓
DAX Measures Development
↓
Dashboard Development
↓
Interactive Filters & Slicers
↓
Final Dashboard Formatting
```

---

# 📌 Data Modeling

The project follows a structured data model using:
- Fact Tables
- Dimension Tables
- Relationships
- Star Schema Modeling

---

# 📌 Calculated Columns

## Cost Bucket

```DAX
Cost Bucket =
SWITCH(
    TRUE(),
    Restaurants[CostForTwo] < 500, "Budget",
    Restaurants[CostForTwo] < 1000, "Mid Range",
    "Premium"
)
```

---

## Rating Bucket

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

## Delivery Status

```DAX
Delivery Status =
IF(Orders[DeliveryTimeMins] > 45, "Late", "On Time")
```

---

# 📌 Core DAX Measures

## KPI Measures

```DAX
Total Orders =
COUNT(Orders[OrderID])

Total Revenue =
SUM(Orders[OrderValue])

Avg Order Value =
DIVIDE([Total Revenue], [Total Orders])

Avg Delivery Time =
AVERAGE(Orders[DeliveryTimeMins])

Total Customers =
DISTINCTCOUNT(Orders[CustomerID])

Total Restaurants =
DISTINCTCOUNT(Restaurants[RestaurantID])
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

## Operational Measures

```DAX
Late Orders =
CALCULATE(
    [Total Orders],
    Orders[Delivery Status] = "Late"
)

Cancelled Orders =
CALCULATE(
    [Total Orders],
    Orders[OrderStatus] = "Cancelled"
)

Late Delivery % =
DIVIDE([Late Orders], [Total Orders])

Cancellation % =
DIVIDE([Cancelled Orders], [Total Orders])
```

---

# 📈 Key Business Insights

- Identified high-performing restaurants and cuisines
- Analyzed customer retention and repeat behavior
- Evaluated delivery efficiency and operational delays
- Tracked cancellation trends across cities
- Compared revenue performance across pricing categories
- Monitored customer spending behavior
- Evaluated restaurant ratings and customer satisfaction

---

# 🚀 Business Impact

This dashboard helps businesses:
- Improve operational efficiency
- Optimize delivery performance
- Monitor restaurant growth
- Understand customer behavior
- Increase customer retention
- Support data-driven business decisions
- Improve logistics and operational planning

---

# 🎯 Skills Demonstrated

- Data Cleaning & Transformation
- Data Modeling
- DAX Calculations
- Business Intelligence
- Dashboard Development
- Data Visualization
- KPI Development
- Time-Series Analysis
- Business Analytics
- Interactive Reporting

---

# 📂 Dataset

- Real-world Food Delivery Dataset from Kaggle

---

# 📌 Project Status

✅ Completed Successfully

---

# 🔗 Connect With Me

## LinkedIn
https://www.linkedin.com/in/ramesh2026/
