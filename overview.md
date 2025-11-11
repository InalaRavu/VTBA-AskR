Data is pulled from various sources (Edwards, Leybold, Hana, Hubspot, C4C) and written into the Lake using Velocity, ADF, API, IR, etc. during the ingestion layer. All data is stored in the staging area, which has been logically separated into three layers: 
    Raw (raw data)
    Trusted (CDM data)
    Refined (to fulfill customer requirements)
Data curation is performed using Databricks, which reads data from the Raw layer and curates it into CDM. The CDM data is then further curated into the Refined layer for business consumption. End users can access the views via Databricks for Power BI consumption.