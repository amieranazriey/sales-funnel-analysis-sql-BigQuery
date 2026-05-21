# sales-funnel-analysis-sql-BigQuery
This repository contains SQL queries designed to analyze e-commerce sales performance and customer conversion traffic over a rolling 30-day period using Google BigQuery.

Based on latest 30-day performance data, the storefront achieved the following benchmarks:
*   **Total Visitors:** 4,268 unique users
*   **Total Conversion Rate:** 16.59% (708 unique buyers)
*   **Average Order Value (AOV):** $107.40
*   **Revenue Per Visitor (RPV):** $17.82
*   **Total Revenue:** $76,037.93

Business Insights
1. **Zero Repeat Cohorts:** The data shows `total_buyers` and `total_orders` are identical (708). This indicates that every customer placed exactly one order during this 30-day window, highlighting an opportunity to build retention/email marketing campaigns.
2. **Highly Efficient Acquisition:** With an RPV of $17.82, the business can safely scale marketing spend. If a target Customer Acquisition Cost (CAC) is capped at $50, the first transaction still yields a positive contribution margin of $57.40 before product/shipping costs.

3. How to Run the Scripts
The main analytical script is located in `sales_funnel_30_day_metrics.sql`. 
* **Environment:** Google BigQuery
* **Source Table:** `salesfunnelanalysis-sql.sql_projects.sales_funnel`
* **Features Used:** Common Table Expressions (CTEs), Conditional Aggregation (`COUNT(DISTINCT CASE WHEN...)`), and division-by-zero protection (`SAFE_DIVIDE()`).
