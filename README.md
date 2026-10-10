# Retail Sales & Customer Performance Dashboard

## Executive Summary
This project delivers an end-to-end data analytics solution examining over 15,000 retail transactional records. Using Advanced Excel, Power Query, Power BI, and Generative AI, raw data was cleaned, modeled, and visualized into an interactive multi-page dashboard. The insights help executive stakeholders track overall sales performance, analyze monthly revenue growth, monitor customer retention, and optimize inventory for seasonal peak demand.

---

## Key Features & Highlights

* **Data Integrity & Transformation:** Cleaned and transformed 15,000+ transactional records using Power Query and Advanced Excel to ensure 100% data integrity (handled missing values, normalized customer IDs, and unified date formats).
* **Interactive Power BI Dashboard:** Built a dynamic multi-page dashboard featuring KPI cards, monthly trend graphs, RFM-based customer retention metrics, and regional drill-downs.
* **DAX & GenAI Optimization:** Utilized Generative AI prompts (ChatGPT / Claude) to write and optimize complex DAX measures (YTD Sales, YoY Growth %, Cohort Retention Rates, and Rolling 3-Month Averages).
* **Actionable Business Insights:** Identified crucial seasonal purchasing peaks (Q4 holiday surges) and provided data-driven inventory adjustments to maximize revenue opportunities and reduce stockouts.

---

## Tech Stack & Tools Used

* **Data Processing & ETL:** Microsoft Excel, Power Query
* **Data Visualization & BI:** Power BI Desktop, DAX
* **Generative AI:** OpenAI ChatGPT (DAX optimization & Automated Executive Summaries)
* **Documentation & Version Control:** Git, GitHub, Markdown

---

## Data Architecture & DAX Measures Used

### Core DAX Expressions:

1. **Total Revenue:**
   ```dax
   Total Revenue = SUM(Sales[Line Total])
   YoY Growth % = 
VAR CurrentSales = [Total Revenue]
VAR PreviousSales = CALCULATE([Total Revenue], SAMEPERIODLASTYEAR('Calendar'[Date]))
RETURN
DIVIDE(CurrentSales - PreviousSales, PreviousSales, 0)
Retention Rate % = 
VAR ActiveCustomers = DISTINCTCOUNT(Sales[CustomerID])
VAR RepeatCustomers = CALCULATE(DISTINCTCOUNT(Sales[CustomerID]), Sales[PurchaseCount] > 1)
RETURN
DIVIDE(RepeatCustomers, ActiveCustomers, 0)

End-to-end retail data analytics project processing 15,000+ transactional records using Excel, Power Query, and Power BI. Features interactive multi-page dashboards, DAX revenue metrics, GenAI-optimized calculations, and seasonal inventory insights.
