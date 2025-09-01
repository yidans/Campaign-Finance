# Campaign Finance Networks: House of Representatives (2007–2022)

This repository contains datasets and network files used in the study of **intra-party campaign money flow networks (MFNs)** among elected members of the U.S. House of Representatives. The study covers seven midterm election cycles between 2007–2008 and 2021–2022.  

Two complementary data formats are provided:  
- **CSV files** — cleaned tabular datasets of member-to-member contributions and attributes.  
- **GraphML files** — directed network objects for direct use in network analysis or visualization tools.  

The data and workflow replicate the analysis described in the accompanying manuscript, where MFNs are modeled using **Exponential Random Graph Models (ERGMs)**.

---

## Repository Structure

### CSV Datasets

Each file contains contribution records and member identifiers for one election cycle.  

- `df07_08.csv` — General election winners of 2008 (111th Congress) and contributions in 2007–2008  
- `df09_10.csv` — General election winners of 2010 (112th Congress) and contributions in 2009–2010  
- `df11_12.csv` — General election winners of 2012 (113th Congress) and contributions in 2011–2012  
- `df13_14.csv` — General election winners of 2014 (114th Congress) and contributions in 2013–2014  
- `df15_16.csv` — General election winners of 2016 (115th Congress) and contributions in 2015–2016  
- `df17_18.csv` — General election winners of 2018 (116th Congress) and contributions in 2017–2018  
- `df19_20.csv` — General election winners of 2020 (117th Congress) and contributions in 2019–2020  
- `df21_22.csv` — General election winners of 2022 (118th Congress) and contributions in 2021–2022  

**Main fields**:  
- `SEND_ID` — FEC candidate ID of the representative sending contributions  
- `RECEIVE_ID` — FEC candidate ID of the representative receiving contributions  

---

### GraphML Network Files

GraphML files provide **directed money flow networks (MFNs)** for each election cycle.  

**Naming convention**:  
- `XX_YYM1d.graphml`  
  - `XX_YY` = election cycle years (e.g., `09_10`)  
  - `M1` = Model 1 specification  
  - `d` = directed network  

Example:  
- `09_10M1d.graphml` → 2009–2010 cycle, directed MFN of House members  
- `21_22M1d.graphml` → 2021–2022 cycle, directed MFN of House members  

**Network structure**:  
- **Nodes** = Elected House members (general election winners).  
- **Edges** = Directed contributions, where node *i* contributed via a committee to node *j*.  

**Node attributes include**:  
- `CAND_ID` — Candidate identifier (FEC)  
- `CAND_OFFICE_ST` — State  
- `CAND_PTY_AFFILIATION` — Party affiliation  
- `CANDIDATE.NAME..Last..First.` — Candidate name  
- `chairs_next`, `chairs_now` — Committee/leadership chair status  
- `cumulative_occurrence` — Seniority (terms served)  
- `degree_in`, `degree_out` — In/out degree  
- `pagerank`, `katz` — Centrality measures  
- `SupPAC` — Number of distinct supporting/attacking SuperPACs  
- `X24A`, `X24E` — Number of unique SuperPACs making independent expenditures **against** (`24A`) or **supporting** (`24E`) the representative  
- `total` — Total dollar amount of SuperPAC spending (USD)  
- `total_24a_positive` — Total dollar amount of **opposing** expenditures (1000 USD)  
- `total_24e_positive` — Total dollar amount of **supporting** expenditures (1000 USD)  

