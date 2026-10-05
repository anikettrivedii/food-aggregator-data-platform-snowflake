# food-aggregator-data-platform-snowflake
End-to-end Snowflake data engineering platform for a food aggregator, covering CSV ingestion, staging, CDC/Delta processing, data cleansing, dimensional modeling, fact and dimension tables, and analytics.


<div align="center">

# 🍽️ Food Aggregator Data Platform

### End-to-End Data Engineering Project using Snowflake

<p>
  <img src="https://img.shields.io/badge/Snowflake-Data%20Platform-29B5E8?style=for-the-badge&logo=snowflake&logoColor=white" alt="Snowflake">
  <img src="https://img.shields.io/badge/SQL-Data%20Engineering-336791?style=for-the-badge&logo=postgresql&logoColor=white" alt="SQL">
  <img src="https://img.shields.io/badge/Streams-CDC-00A36C?style=for-the-badge" alt="Snowflake Streams">
  <img src="https://img.shields.io/badge/SCD-Type%202-6C63FF?style=for-the-badge" alt="SCD Type 2">
  <img src="https://img.shields.io/badge/Star%20Schema-Data%20Warehouse-F59E0B?style=for-the-badge" alt="Star Schema">
  <img src="https://img.shields.io/badge/Streamlit-Analytics-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" alt="Streamlit">
</p>

<p>
  <b>Raw Data → Incremental CDC → Transformation → Dimensional Modeling → Analytics</b>
</p>

<br>

<img src="https://img.shields.io/badge/Domain-Data%20Engineering-blue?style=flat-square">
<img src="https://img.shields.io/badge/Architecture-Layered-orange?style=flat-square">
<img src="https://img.shields.io/badge/Model-Star%20Schema-success?style=flat-square">
<img src="https://img.shields.io/badge/Processing-Incremental-purple?style=flat-square">

</div>

---

# 📌 Overview

This project demonstrates an **end-to-end Snowflake data engineering platform** designed around a food-aggregator business use case.

The platform takes synthetic operational data representing customers, restaurants, menus, orders, locations, delivery agents, and delivery transactions and transforms it into an **analytics-ready data warehouse**.

The pipeline supports:

- Initial data loading
- Incremental / delta processing
- Change Data Capture using Snowflake Streams
- MERGE-based synchronization
- Data cleansing and standardization
- SCD Type 2 historical tracking
- Star-schema dimensional modeling
- SQL-based analytical views
- Streamlit-based business analytics

The overall architecture follows:

```text
                    ┌──────────────────────┐
                    │    SOURCE DATA       │
                    │  Synthetic CSV Files │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │  SNOWFLAKE STAGE     │
                    │     Raw Landing       │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │       CLEAN          │
                    │ Transformation Layer │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │    CONSUMPTION       │
                    │  Facts + Dimensions  │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │      ANALYTICS       │
                    │ SQL Views + Streamlit│
                    └──────────────────────┘
