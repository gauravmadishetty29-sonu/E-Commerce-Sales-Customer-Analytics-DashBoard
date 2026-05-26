# E-Commerce-Sales-Customer-Analytics-DashBoard

##  Overview
This Power BI dashboard analyzes sales, customer behavior, product performance, delivery status, and cancellations using Orders, Customers, and Products datasets.

The dashboard enables interactive business analysis through KPIs, slicers, and visual storytelling.

---

#  Datasets Used

### Orders Dataset
- OrderID
- CustomerID
- ProductID
- Quantity
- Purchase Date
- Delivery Status

### Customers Dataset
- CustomerID
- Name
- City
- State
- Phone Brand
- Operating System

### Products Dataset
- ProductID
- Product Name
- Category
- Price
- Rating

---

#  Data Model

Relationships:
- Orders → Customers using `CustomerID`
- Orders → Products using `ProductID`

Star schema modeling was used for better performance.

---

#  KPIs

- Total Revenue
- Average Revenue per Order
- Cancellation Rate
- Revenue Lost Due to Cancellation
- Delivery Rate %

---

#  Dashboard Analysis

## Revenue by Product
- Identifies top-performing products
- Mobile products generate highest revenue

## Revenue by Category
- Categories analyzed:
  - Mobile
  - Accessories
  - Headphones
  - Chargers

## Revenue Trend Analysis
- Yearly
- Quarterly
- Monthly trends

## Revenue by State
- Compares regional sales performance

## Delivery vs Cancellation
- Tracks operational efficiency
- Measures cancellation impact

---

#  Interactive Features

### Slicers
- Product Category
- Date Filters

### Features
- Dynamic filtering
- Drill-down analysis
- KPI cards
- Interactive charts

---

#  DAX Measures

## Revenue
```DAX
Revenue = SUMX(Orders, Orders[Quantity] * RELATED(Products[Price]))
```

## Average Revenue
```DAX
AverageRevenueOrder = DIVIDE([Revenue], COUNT(Orders[OrderID]))
```

## Cancellation Rate
```DAX
Cancellation Rate =
DIVIDE(
    COUNTROWS(FILTER(Orders, Orders[Delivery Status] <> "Delivered")),
    COUNTROWS(Orders)
) * 100
```

---

#  Key Insights

- Revenue generated: **1.77B**
- Average order revenue: **112K**
- Cancellation rate: **30%**
- Revenue loss due to cancellations: **525M+**
- Mobile category dominates sales

---

#  Tools Used

| Tool | Purpose |
|---|---|
| Power BI | Dashboard Development |
| Power Query | Data Transformation |
| DAX | KPI Calculations |
| CSV Files | Data Source |

---

#  Project Structure


---

#  Conclusion

This dashboard converts raw business data into actionable insights using Power BI visualizations, KPI tracking, and interactive analysis to support data-driven decision making.
