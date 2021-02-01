---
title: "polaris_approach"
author: "Erica"
date: "1/31/2021"
---

# Goal: 
## Determine which company or combination of companies lead to the sum-total of X points to meet the threshold score for Polaris GWAC. 

> Note: Criteria for selection (see Section L) have been defined. Weights (see "Number of Potential Occurences" in M.6 Scoring Table) have been defined However, the Scoring Values have yet to be released. Will move forward with calculating points as soon as they are released. 

# Approach: 

## Part 1: Filter companies with projects that meet Section L (VOL 1 - VOL 5)

### Data Required
- AWARDS DATA USASPENDING.GOV FY08-21
- CMMI
- SAM DATA SAM.GOV
- CPARS DATA CPARS.GOV (NOTE: MAY NOT BE PUBLIC)
	
### Interpretation & Algorithms

#### VOL 1 GENERAL
TBD

#### VOL 2 RELEVANT EXPERIENCES (L_5_2)
- L_5_2_2 = "Primary Relevant Experience" 
-  ≤ 7 ∃! Project 
- Where each Project =
  - ≥ 1 NAICS = 518210 | 541511 | 541512 | 541513 | 541519
  - ≥ Project per 2016-2021 range & ≥ 1 y duration
  - ≥ 1 M USD
- See M.6 SCORING TABLE for details
  - L_5_2_2_2 = Project Size and Complexity
    - Max 7 occurrences/project
  - L_5_2_2_3 = Experience Working with Multiple Federal Government Customers
    - Max 5 occurrences/project
  - L_5_2_2_4 = Cost-Reimbursement
    - Max 2 occurrences/project
  - L_5_2_2_5 = Task Order against a Multiple-Award IDIQ Contract
    - Max 7 occurrences/project
  - L_5_2_2_6 = OCONUS Project
    - Max 1 occurrences/project
  - L_5_2_2_7 = Project with subcontracting
    - Max 3 occurrences/project
  - L_5_2_2_8 = Project with Cloud Services
    - Max 3 occurrences/project
  - L_5_2_2_9 = Project with Cybersecurity Services
    - Max 3 occurrences/project
  - L_5_2_2_10 = Breadth of Relevant Experience Performance Areas
    - Max 1 occurrences/project


- L_5_2_3 = "Emerging Technology Relevant Experience"
- ≥ 150 K USD per project
- ≥ 1 INNOVATIVE SOLUTIONS (SEE ["polaris_c_algorithm.txt"](https://github.com/ericaosta/alagant/blob/main/polaris_c_algorithm.txt))
- See M.6 SCORING TABLE
  - L_5_2_3_3 = "Breadth of Emerging Technology Relevant Experience"
    - Max 1 occurrences/project

#### VOL 3 PAST PERFORMANCE (L_5_3)
- VOL 3 ⊆ VOL 2
- IF (primary source == CPARS in X) then CPARS, ELSE (primary source == 'other' in X) then PP_SURVEY
  - *X = CPARS.GOV data matched to (AWARD ID|CONTRACT ID) & DUNS*
- See M.6 SCORING TABLE
  - L_5_3_1 - _3 = Past Performance
    - Max 1 occurrences/project

#### VOL 4 SYS, CERT, CLEAR (L_5_4)
- Cost Accounting Systems = ("COST"&"ACCOUNT")|SYS"
- Facility Clearance = "FACILIT"&"CLEARANC"|"FLC"
- Purchasing Systems = "PURCHAS"&"SYS"
- CMMI ≥ ML2
- ISO 9001:2015|20000:2018|27001:2018
- See M.6 SCORING TABLE
  - L_5_4_1 = Systems
    - Max 1 occurrences/project
  - L_5_4_3 - 5 = Industry Certifications (CMMI, ISO)
    - Max 1 occurrences/project
  - L_5_4_7 = Government Facility Clearances
    - Max 1 occurrences/Project
    
#### VOL 5 RISK ASSESSMENT (L_5_5)
- VOL 5 ⊆ VOL 3
- CREDIT TBD
- See M.6 SCORING TABLE
  - L_5_5_1 = Organizational Risk Assessment 
    - Max 1 occurrences/project
  - L_5_5_2 Limitations on Subcontracting Compliance Risk
    - Max 1 occurrences/project
	
## Part 2: Determine Scores as in M.6 SCORING TABLE

### Data Required
- AWARDS DATA USASPENDING.GOV FY08-21
- CMMI DΑΤΑ
- SAM DATA SAM.GOV
- CPARS DATA CPARS.GOV (NOTE: MAY NOT BE PUBLIC)
	
### Interpretation & Algorithms

#### Best Value	For Polaris, Highest Technically Rated Qualifying Offerors ==
- FAR 15.101 = 1 | >1 ∃! company (i.e., "source selection approach") combo 
- IF ELSE looped through all possible combinations 
- IF (company 1 ≥ "threshold score") THEN "HTRQO", ELSE (company 1 + company N + ... ≥ "threshold score") THEN "HTRQO"
				
#### Polaris	= 3 MA/IDIQ contracts (POOLS) 
- 1 MA/IDIQ contract (POOL) ≥ 1 awards

