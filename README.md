## Phase 1: Ask
**Goal:** Define the problem and set the focus of the analysis.  

- **Steps Taken:**  
  - Identified rising concern around housing instability in NYC  
  - Narrowed focus to eviction trends between 2017–2024  
  - Framed guiding questions:  
    - How have eviction rates changed over time?  
    - Which boroughs are most affected?  
    - What external factors (e.g., COVID-19 moratoriums) influenced the data?  

- **Implications:**  
  - Establishes a clear research scope  
  - Aligns project with real-world policy and community relevance  

---

## Phase 2: Prepare
**Goal:** Collect, clean, and organize the eviction dataset for analysis.  

- **Steps Taken:**  
  - Acquired NYC eviction dataset (2017–2024)  
  - Verified completeness and consistency of fields (borough, year, property type, counts)  
  - Standardized formats for dates, borough codes, and property classifications  
  - Documented data dictionary and assumptions for clarity  

- **Implications:**  
  - Ensures data reliability for downstream analysis  
  - Creates a clean foundation for reproducible queries and insights  

---

## Phase 3: Process
**Goal:** Transform and structure the dataset for deeper analysis.  

- **Steps Taken:**  
  - Created SQL tables for borough, property type, and yearly counts  
  - Used CTEs to break down eviction counts by year and borough  
  - Applied functions (e.g., regex_replace) to clean inconsistencies  
  - Prepared queries to compare pre-, during-, and post-pandemic periods  

- **Deliverables:**  
  - SQL scripts for structured tables and cleaned outputs  
  - Dataset ready for exploratory analysis  

---

## Phase 4: Analyze
**Goal:** Apply analytical techniques to identify trends, patterns, and insights.  

- **Steps Taken:**  
  - Aggregated eviction counts by year and month to observe temporal trends  
  - Grouped data by borough to assess geographic differences  
  - Compared residential vs. commercial eviction ratios  
  - Checked for seasonal variations across years  

- **Findings:**  
  - Temporal: Evictions declined sharply in 2020–21, rose again post-2022, still below 2017 levels  
  - Geographic: Bronx & Brooklyn consistently report the highest eviction counts  
  - Property Type: Residential evictions dominate over commercial cases  
  - Seasonal: No strong seasonal pattern detected; external events (e.g., moratoriums) had larger effects  

- **Implications:**  
  - Trends can guide policy evaluation and resource allocation  
  - Borough analysis identifies “eviction hotspots” for targeted support  
  - Residential focus highlights direct links to housing instability  

---

## Phase 5: Share
**Goal:** Communicate findings effectively to the intended audience.  

- **Methods of Sharing:**  
  - Executive summary for policymakers  
  - Visualizations (time-series charts, borough maps, comparisons by period)  
  - Concise, clear language to ensure accessibility for non-technical readers  

- **Data Story:**  
  - Evictions are a persistent challenge in NYC  
  - COVID-19 moratoriums caused a temporary sharp decline  
  - Eviction rates are rising again toward pre-pandemic levels  
  - Bronx & Brooklyn remain most affected  

- **Planned Deliverables:**  
  - Comprehensive written report  
  - Presentation deck with visuals  
  - Open-access repository with SQL scripts, cleaned data, and charts  

---

## Phase 6: Act
**Goal:** Translate insights into practical recommendations and next steps.  

- **Conclusions:**  
  - External events (pandemic, moratoriums) significantly impacted eviction rates  
  - Evictions remain concentrated in Bronx & Brooklyn  
  - Rates are trending upward, signaling ongoing housing instability  

- **Recommendations for Stakeholders:**  
  - Expand rental assistance and prevention programs in high-impact boroughs  
  - Pilot targeted interventions and measure effectiveness  
  - Strengthen tenant protections in eviction hotspots  

- **Next Steps:**  
  - Convene policymakers, legal aid, and community leaders for discussion  
  - Integrate eviction dataset with additional sources (filings, demographics, rental prices, court outcomes)  
  - Monitor trends beyond 2024 to evaluate long-term housing stability  
