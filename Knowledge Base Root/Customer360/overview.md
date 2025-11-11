# Customer360 — Data Ingestion & Curation Overview

## Sources & Ingestion
- Source systems: Edwards, Leybold, Hana, Hubspot, C4C
- Ingestion mechanisms: Velocity, Azure Data Factory (ADF), APIs, IR, etc.
- Data is written into the Lake during the ingestion layer and landed in the staging area.

## Staging area (logical separation)
- Raw — raw, untransformed source data (landing zone)
- Trusted — curated into Common Data Model (CDM) structures
- Refined — business-ready artifacts optimized to fulfill customer requirements

## Data curation & processing
- Databricks reads Raw data and performs curation into CDM (Trusted).
- Further transformations in Databricks produce Refined datasets and views for consumption.
- Flow: Source systems -> Ingestion (Velocity/ADF/API/IR) -> Raw -> Databricks curation -> Trusted (CDM) -> Databricks transforms -> Refined

## Consumption
- End users access curated views via Databricks for Power BI consumption.

## Notes / Recommendations
- Keep Raw immutable; implement versioning and lineage.
- Enforce schema and quality checks during curation to Trusted (CDM).
- Expose Refined datasets as documented views for Power BI and downstream consumers.
- Monitor ingestion pipelines and Databricks jobs for latency and failures.
- Document CDM mappings and transformation logic alongside the Refined outputs.
