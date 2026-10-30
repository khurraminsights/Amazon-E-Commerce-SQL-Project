<div align="center">

# Amazon E-Commerce | SQL & Power BI Analytics

### Sales Performance · Product Profitability · Customer Insights · Regional Intelligence

![SQL Server](https://img.shields.io/badge/SQL_Server-T--SQL-CC2927?style=for-the-badge)
![Power BI](https://img.shields.io/badge/Power_BI-Business_Intelligence-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Analytics](https://img.shields.io/badge/Analytics-E--Commerce-1476A8?style=for-the-badge)
![Portfolio](https://img.shields.io/badge/Project-Portfolio_Case_Study-202C45?style=for-the-badge)

**A business-focused e-commerce analytics portfolio project combining SQL analysis with Power BI reporting to explore sales, customer value, product performance and regional opportunities.**

[Business Problem](#business-problem) · [Dashboard](#power-bi-dashboard) · [SQL Questions](#sql-business-questions) · [Insights](#analytical-observations) · [Recommendations](#business-recommendations)

</div>

> **Independent portfolio project.** “Amazon” is used as the business theme of this case study, not as evidence of employment, sponsorship or access to Amazon internal systems. Figures in the supplied dashboard are presented as *dashboard illustrations* and have not been reconciled against underlying source data in this review.

---

## Executive Summary

E-commerce teams need to understand where revenue originates, which products are truly profitable, what customers buy repeatedly, and how demand differs across regions.

This project connects **SQL-based investigation** with a **multi-view Power BI dashboard** to answer those questions. The SQL presentation includes product, customer, review, wishlist, discount, time-series, profit and geography analyses. The supplied Power BI design presents three major reporting areas: executive overview, product profitability and regional performance.

**My role:** Data Analyst  
**Tools represented:** SQL and Power BI  
**Industry:** E-commerce / retail analytics  
**Business outcome:** An analytical reporting concept and portfolio case study, rather than a verified deployed solution.

### What I worked on

- Framed business questions around sales, products, customers, discounts and regional performance.
- Used SQL analytical approaches to rank and aggregate business activity.
- Organized KPIs and visual narratives for Power BI reporting.
- Interpreted product profitability and customer-spend patterns.
- Identified areas where reporting definitions and data validation should be strengthened.

---

## Business Problem

A sales total alone cannot explain business performance. Decision-makers also need to know:

1. Which products drive **unit volume**, and are those also the most profitable?
2. Who are the highest-spending customers?
3. What do product ratings, reviews and wishlists suggest about demand?
4. How do discounts change reported sales value?
5. Which products have weak sales or thin margins?
6. How do revenue and profit vary by month and region?
7. Which product categories contribute most to profit?
8. How do selling prices relate to quantity sold?

---

## Analytical Workflow

```text
        E-COMMERCE BUSINESS DATA
     Products | Orders | Customers
        Reviews | Wishlists | Costs
                    |
               SQL ANALYSIS
                    |
       +------------+-------------+
       |            |             |
    Sales &      Customers     Product &
    Trends       & Demand      Profitability
       |            |             |
       +------------+-------------+
                    |
             POWER BI REPORT
                    |
      Executive | Product | Region
                    |
        BUSINESS INTERPRETATION
```

*Conceptual workflow. The supplied presentation includes a database-diagram slide; exact table keys and production relationships should be confirmed from the underlying SQL/database files.*

---

## Power BI Dashboard

### Dashboard showcase

![Amazon E-Commerce Business Overview, Product Profitability and Regional Performance](assets/amazon-dashboard-overview.jpg)

*The supplied image combines three dashboard views. It serves as a portfolio visual reference; displayed KPI values have not been independently validated against SQL outputs.*

### Page 1 — Executive Overview

**Goal:** Give decision-makers a concise view of commercial performance.

**Displayed KPIs**
- Total revenue
- Total profit
- Total orders
- Total customers
- Average order value
- Average profit margin

**Visuals and controls**
- Monthly sales trend
- Top-selling products by quantity
- Date range, category and region filters
- Navigation to sales, product, customer and regional analysis

### Page 2 — Product & Profitability Insights

**Goal:** Separate high-selling products from high-profit products.

**Displayed analysis**
- Product-level revenue, cost, profit and margin
- Highest-margin products
- Profit by product category

**Decision use:** Compare commercial volume with profitability to guide assortment, pricing and promotion reviews.

### Page 3 — Regional Performance

**Goal:** Compare performance across geographic markets.

**Displayed analysis**
- Geographic sales distribution map
- Regional sales comparison chart
- Cross-market performance view

**Decision use:** Investigate which regions merit closer analysis, taking into account market coverage and underlying transaction volume.

> **Quality note:** Several values and labels in the supplied composite image appear inconsistent or hard to reconcile (including unit labels, repeated geography names and some financial table figures). They should be corrected in Power BI before the screenshot is presented as a validated financial report.

---

## SQL Business Questions

The supplied presentation contains the following analytical questions. They are consolidated below by topic; duplicate questions from the slides are identified rather than counted as separate unique analyses.

| Area | SQL analysis | Intended business use |
|---|---|---|
| **Sales volume** | Top 5 products by quantity sold | Identify high-volume products |
| **Customer value** | Top 5 customers by total spend | Understand revenue concentration |
| **Customer feedback** | Average product rating | Monitor perceived product quality |
| **Demand signals** | Top 5 most-wishlisted products | Explore interest beyond completed purchases |
| **Discounts** | Sales before vs. after discounts | Evaluate price reductions and net sales |
| **Underperformers** | Products below a sales-volume threshold | Investigate low-demand inventory |
| **Regional sales** | Sales by city or country | Compare market performance |
| **Time series** | Monthly sales in the past 12 months | Identify change and seasonality |
| **Profitability** | Profit by product | Measure revenue less recorded cost |
| **Customer value** | Total customer spend over time | Describe historical customer value |
| **Margins** | Highest profit-margin products | Compare relative profitability |
| **Price vs. demand** | Product price and quantity sold | Explore association, not causation |
| **Review quality** | Average rating and review counts | Compare feedback volume and score |
| **Category profit** | Total profit by category | Identify categories contributing profit |

**Slide note:** The PowerPoint numbers business questions as 1–12 and 14–18, skipping 13, and repeats monthly and regional sales questions. This README groups them into **14 distinct analytical themes** without claiming 18 independently verified queries.

---

## SQL Analytical Methodology

These are techniques appropriate to the project questions. The PowerPoint does not expose enough executable query text to verify every exact statement.

| Technique | Typical application |
|---|---|
| `SUM()` and `COUNT()` | Revenue, orders, units and customers |
| `AVG()` | Ratings and mean order values |
| `GROUP BY` | Category, product, region and month breakdowns |
| `ORDER BY` and `TOP` | Top products, customers and margins |
| JOINs | Combine products, transactions, customers and reviews |
| Date functions | Monthly reporting and 12-month filtering |
| Calculated expressions | Discounts, profit and margin |
| Conditional filtering | Low sales, category selection and periods |

### Key metric definitions to validate

| KPI | Recommended definition |
|---|---|
| **Gross sales** | Sum of transaction value before discounts |
| **Net sales** | Gross sales minus applicable discounts and adjustments |
| **Profit** | Net sales minus defined cost components |
| **Profit margin %** | Profit ÷ net sales × 100, when net sales is nonzero |
| **Average order value** | Net sales ÷ distinct orders |
| **Historical customer spend** | Sum of recognized net sales per customer |
| **Customer lifetime value** | Requires a defined period and/or predictive model; historical spend alone is not predictive CLV |

### Example analysis pattern: product profitability

```sql
-- Illustrative T-SQL template; map fields to the real schema.
SELECT
    ProductID,
    SUM(NetSales) AS NetRevenue,
    SUM(CostAmount) AS TotalCost,
    SUM(NetSales - CostAmount) AS Profit,
    100.0 * SUM(NetSales - CostAmount)
        / NULLIF(SUM(NetSales), 0) AS ProfitMarginPct
FROM SalesFact
GROUP BY ProductID
ORDER BY Profit DESC;
```

The example uses **illustrative** `SalesFact` and column names; these were **not verified against the presentation's schema**. Actual SQL files should determine the exact query.

---

## Analytical Observations

The supplied dashboard illustrates these areas:

**Sales performance:** A monthly trend and top-products chart provide a starting point for examining seasonality and sales concentration.

**Product profitability:** Product-level revenue, cost and profit views help distinguish volume from margin performance.

**Regional comparison:** A map and market comparison chart support geographic analysis, but the image alone cannot establish actual company market shares.

**Customer and demand analytics:** The SQL-question set extends beyond revenue into reviews, wishlists and customer spend. The supplied dashboard composite does not provide a complete customer-detail page, so those findings should be supported with SQL results or additional Power BI screenshots.

**Important:** Exact numerical claims such as total revenue, growth percentages, profit margin and market concentration should be treated as unverified until reconciled with the database and Power BI measures.

---

## Business Recommendations

| Opportunity | Suggested action | Metric to monitor |
|---|---|---|
| **High-volume products** | Compare stock availability with sales volume | Units sold, stockouts |
| **Low-margin products** | Review pricing, discounts and attributable costs | Profit margin % |
| **High-value customers** | Examine repeat purchasing and retention opportunities | Repeat rate, customer spend |
| **Wishlisted products** | Compare customer interest with conversions | Wishlist-to-purchase rate |
| **Regional performance** | Investigate market-level differences before allocating campaigns | Net sales, orders and margin by region |
| **Customer feedback** | Examine low-rating products with sufficient review counts | Rating, reviews, returns |
| **Monthly volatility** | Compare promotions, seasonality and product mix | Monthly net sales and growth |

These are business proposals informed by the report's analytical structure, **not measured improvements attributed to the project**.

---

## Validation & Reporting Improvements

Before positioning the dashboard as a final decision-support report:

- [ ] Verify SQL table names, primary keys and relationships against the database.
- [ ] Reconcile SQL revenue, profit, order and customer totals with Power BI.
- [ ] Clearly distinguish gross sales, net sales, profit and margin.
- [ ] Correct inconsistent financial units and regional labels in the dashboard.
- [ ] Ensure all filters affect the intended visuals.
- [ ] Confirm Top 5 logic uses the correct measure and tie handling.
- [ ] Show a clear time period for monthly trends.
- [ ] Validate customer spend vs. lifetime value terminology.
- [ ] Include actual SQL scripts and a reproducible data dictionary.
- [ ] Publish revised screenshots generated directly from Power BI Desktop.

---

## Technical Competencies

**SQL Analytics:** filtering, aggregations, ranking, joining transactional tables, calculations, time-based reporting and product analysis.

**Power BI:** KPI cards, line and bar charts, product profitability tables, region maps, filters and report navigation.

**Business Analysis:** defining KPIs, evaluating product performance, interpreting customer activity, identifying reporting limitations and developing practical follow-up questions.

---

## Repository Contents

| Resource | Purpose |
|---|---|
| `README.md` | Project story, methods, findings, limitations and recommendations |
| `assets/amazon-dashboard-overview.jpg` | Supplied Power BI dashboard collage |
| `AmazonEcommerce.pptx` | SQL business-question walkthrough and database-diagram presentation |

*The presentation and dashboard image are available in the accompanying package. An executable SQL script and PBIX report were not attached in this request; add those original files if available.*

---

## Future Work

1. **SQL reproducibility:** Include the source SQL script, database structure, sample data and validation results.
2. **Power BI accuracy:** Correct measure definitions, category labels, region names and units.
3. **Customer analysis:** Add repeat orders, cohort retention and product-review pages where supported by data.
4. **Documentation:** Publish a data dictionary and explain how each important KPI is calculated.
5. **Performance:** Review query execution plans and model relationships for larger datasets.

---

<div align="center">

### About the Analyst

**Khurram Naveed**  
Data Analyst | SQL Server | Power BI | Excel

[![GitHub](https://img.shields.io/badge/GitHub-khurraminsights-181717?style=for-the-badge&logo=github)](https://github.com/khurraminsights)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/khurram-naveed-0083851aa/)

**Business questions → SQL analysis → Power BI reporting → informed decisions**

</div>

