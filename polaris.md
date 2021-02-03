---
title: "polaris_approach"
author: "Erica"
date: "2/03/2021"
---
# Goal
## Determine which company or combination of companies lead to the sum-total of X points to meet the threshold score for Polaris GWAC. 
- [Polaris GWAC Draft Request for Proposals from beta.SAM.gov](https://beta.sam.gov/opp/257509b8cfe14d48beb4f71033995e0b/view?keywords=polaris&sort=-relevance&index=opp&is_active=true&page=1)

> Note: Criteria for selection (see Section L) have been defined. Weights (see "Number of Potential Occurences" in M.6 Scoring Table) have been defined However, the Scoring Values have yet to be released. Will move forward with calculating points as soon as they are released. 


# Initial search for potential TEAM LEADERS
## Data Required
- List of companies from [SAM.gov](https://www.sam.gov/SAM/pages/public/searchRecords/advancedEMRSearch.jsf) that meet the following:
  - Small Business
  - NAICS code: 541512
  - United States
- List of companies with CMMI ML2 and up
  - I can reference my original list from Factor 1 [SAM_CMMI.xlsx](https://github.com/ericaosta/alagant/blob/main/F1/SAM_CMMI.xlsx) and include CMMI ML2 and up
  - I can begin my search agnostic of CMMI status and, after narrowing down based on Small Business, NAICS, Clearances, etc., I can manually check for CMMI and ISO
- List of awards from [USAspending.gov](https://www.usaspending.gov); search under AWARD DESCRIPTION
  - Facility Security Clearance ("TOP SECRET", "SECURITY CLEARANCE", etc.)
  - Cost Accounting System
  - Approved Purchasing System
- Others? Esp. to find FCL. To instance, [state.gov](https://www.state.gov/facility-security-clearances-faq/) states that FCL can be in the form of a formal contract, Request for Proposal (RFP), purchase order, an IDIQ. There is some more info on this discussion on [business.defense.gov](https://business.defense.gov/Portals/57/Documents/SmallBusinessWebinar%20QandA.pdf?ver=2020-07-15-161110-867) but do not know how to appropriately and thoroughly proceed on this item yet.

## Criteria
- **A**. Must be
  - Small Business (SB), 
  - Woman-Owned Small Business (WOSB), and/or 
  - Historically Underutilized Business Zones (HUBZone)
- **B**. L_5_2; Volume 2 (Relevant Experience, NAICS only)
  - **541512**
  - 518210
  - 541511
  - 541513
  541519
- **C**. L_5_4; Volume 4 (Systems, Certifications, Clearances)
  - CMMI ≥ ML2
  - ISO 9001:2015|20000:2018|27001:2018
  - Cost Accounting System
  - Approved Purchasing System
  - Government Facility Clearance (Secret vs. Top Secret)

## Order of Operations
- **Step 1.** List of all companies that are Small Businesses in the USA by NAICS 541512 from SAM.gov
- **Step 2.** Match previous filtered list (Step 1) with awards data from USAspending.gov FY08-21 by PARENT DUNS
- **Step 3.** Filter companies with keyword matches for FCL, Cost Accounting System, Approved Purchasing System (**TBD**) under AWARD DESCRIPTION


AND/OR


- **Step 4.** If list is reasonably short, manually search for CMMI ML2 and up and ISO 9001:2015, 20000:2018, and/or 27001:2018

