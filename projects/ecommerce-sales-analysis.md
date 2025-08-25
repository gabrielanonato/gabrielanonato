---
layout: page
title: E-commerce Sales Analysis (SQL + Power BI)
permalink: /projects/ecommerce-sales-analysis
---

![E-commerce Dashboard](/assets/img/ecommerce-dashboard.png){: .project-hero }

**Goal:** Understand sales performance, AOV, seasonality, and product/category impact.  
**Dataset:** Brazilian E-Commerce Public Dataset by Olist (or similar).  
**Tools:** SQL (joins & CTEs), Power BI, Excel for quick checks.

<div class="kpi">Revenue</div><div class="kpi">Orders</div><div class="kpi">AOV</div><div class="kpi">Repeat Rate</div>

### Business Questions
- What are the top products/categories by revenue and margin?
- How does **AOV** vary by month/channel?
- Is there **seasonality** (monthly/weekly patterns)?
- Which regions/customers contribute most to revenue?

### SQL Highlights (samples)
```sql
-- AOV (Average Order Value)
WITH order_totals AS (
  SELECT
    oi.order_id,
    SUM(oi.price + oi.freight_value) AS order_value
  FROM order_items oi
  GROUP BY 1
)
SELECT AVG(order_value) AS aov
FROM order_totals;
```

```sql
-- Top categories by revenue (last 12 months)
WITH item_rev AS (
  SELECT
    p.product_category_name,
    SUM(oi.price) AS revenue
  FROM order_items oi
  JOIN products p ON p.product_id = oi.product_id
  JOIN orders o ON o.order_id = oi.order_id
  WHERE o.order_purchase_timestamp >= DATEADD(month, -12, CURRENT_DATE)
  GROUP BY 1
)
SELECT * FROM item_rev ORDER BY revenue DESC LIMIT 15;
```

### Power BI Dashboard
**Pages:** Overview · Products · Customers · Seasonality  
**Visuals:** Line (monthly trend), Bar (top categories), Map (region), Matrix (segments)

**Links:** [Queries (GitHub)](<add-link>) · [Power BI (published)](<add-link>)
