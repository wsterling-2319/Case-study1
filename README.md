# 🏠 NYC Eviction Trends Analysis (2017–2024)

## 📌 Project Overview
This capstone project analyzes **publicly available eviction records** from [NYC Open Data](https://opendata.cityofnewyork.us/).  
The goal is to uncover **eviction trends in New York City from 2017–2024**, providing insights for **policymakers, housing advocates, and community organizations** to improve housing stability and prevent homelessness.  

Key study periods:
- **Pre-Pandemic (2017–Feb 2020)**
- **Pandemic/Moratorium (Mar 2020–Aug 2021)**
- **Post-Moratorium (Sep 2021–2024)**

---

## 🎯 Project Goals
- Identify **temporal trends** in executed evictions.  
- Map **geographic distributions** (boroughs, zip codes).  
- Compare **residential vs. commercial** eviction ratios.  
- Provide **data-driven insights** to support policy and advocacy efforts.  

---

## 👥 Key Stakeholders (Hypothetical)
- NYC Department of Housing Preservation & Development (HPD)  
- NYC Public Advocates Office  
- Legal Aid Societies & Tenant Rights Organizations  
- NYC Council Members & State Legislators  
- Community Boards & Neighborhood Associations  
- Homeless Services Providers  

---

## 🧑‍💼 Audience & Impact
The analysis is designed for:
- **Policymakers:** Evaluate resource allocation, policy effectiveness, and service planning.  
- **Legal Aid & Advocacy Groups:** Identify eviction hotspots and strengthen advocacy efforts.  
- **Community & Service Providers:** Support housing initiatives and forecast service needs.  

---

## 📊 Data Source
**Dataset:** NYC Open Data – [Evictions](https://opendata.cityofnewyork.us/)  
Contains records of **executed eviction warrants**.

### Key Columns
- Executed Date  
- Borough  
- Zip Code  
- Residential/Commercial  
- Marshal Details  
- Court Index Number  
- Docket Number  

### Key Metrics
- Total executed evictions (monthly, quarterly, annually).  
- % change (MoM, YoY).  
- Geographic distribution (borough/zip).  
- Residential vs. commercial ratios.  
- Period-specific comparisons (pre-pandemic, pandemic, post-pandemic).  

---

## 🛠️ Workflow

### Phase 1: Ask
- Define problem: **Housing instability driven by evictions.**
- Frame guiding questions and audience impact.

### Phase 2: Prepare
- Data downloaded from NYC Open Data as CSV.  
- Organized into `data/raw/` and `data/processed/`.  
- ROCCC Analysis:  
  - **Reliable:** ✅ Official NYC Marshal records  
  - **Original:** ✅ Primary source  
  - **Comprehensive:** ⚠ Missing reasons & demographics  
  - **Current:** ✅ Updated  
  - **Cited:** ✅ Official attribution  

**Limitations:**  
- Only covers executed evictions (not filings).  
- No demographic data.  
- Limited to zip code precision.  

### Phase 3: Process
Cleaning & transformation steps:
- Converted `executed_date` → Date type.  
- Removed PII.  
- Deduplicated (`case_id`, `docket_number`, `executed_date`).  
- Validated date range (2017–2024).  
- Standardized categorical values (borough, property_type).  
- Filtered for **residential** properties.  

**Sample SQL:**  
```sql
-- Total evictions by borough
SELECT borough, COUNT(*) AS Total_Eviction
FROM evictions
GROUP BY borough;

-- Check for duplicates
SELECT case_id, docket_number, executed_date, COUNT(*) AS Count
FROM evictions
GROUP BY case_id, docket_number, executed_date
HAVING COUNT(*) > 1;
