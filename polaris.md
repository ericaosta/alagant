---
title: "polaris_approach"
author: "Erica"
date: "2/03/2021"
---
# Goal
## Determine which company or combination of companies lead to the sum-total of X points to meet the threshold score for Polaris GWAC. 
- [Polaris GWAC Draft Request for Proposals from beta.SAM.gov](https://beta.sam.gov/opp/257509b8cfe14d48beb4f71033995e0b/view?keywords=polaris&sort=-relevance&index=opp&is_active=true&page=1)

> Note: Criteria for selection (see Section L) have been defined. Weights (see "Number of Potential Occurences" in M.6 Scoring Table) have been defined However, the Scoring Values have yet to be released. Will move forward with calculating points as soon as they are released. 

# Team Lead Search
## 1. Objective
Search will be focused on certifications (e.g., ISO), CMMI maturity levels, clearances, and other yes-or-no objective measures.

## 2. Input Data
- List of companies from [SAM.gov](https://www.sam.gov/SAM/pages/public/searchRecords/advancedEMRSearch.jsf) that meet the following:
  - Small Business
  - NAICS code: 541512
  - United States
- List of companies with CMMI ML3 and up
  - I can reference my original list from Factor 1 [SAM_CMMI.xlsx](https://github.com/ericaosta/alagant/blob/main/F1/SAM_CMMI.xlsx) and include CMMI ML3 and up
  - I can begin my search independen of CMMI status and, after narrowing down based on Small Business, NAICS, Clearances, etc., I can manually check for CMMI and ISO
- List of awards from [USAspending.gov](https://www.usaspending.gov); search under AWARD DESCRIPTION
  - Facility Security Clearance ("TOP SECRET", "SECURITY CLEARANCE", etc.)
  - Cost Accounting System
  - Approved Purchasing System
- Other data to be scraped from web search, company websites, etc., by Andrew as needed
- Others? Esp. to find FCL. For instance, [state.gov](https://www.state.gov/facility-security-clearances-faq/) states that FCL can be in the form of a formal contract, Request for Proposal (RFP), purchase order, an IDIQ. There is some more info on this discussion on [business.defense.gov](https://business.defense.gov/Portals/57/Documents/SmallBusinessWebinar%20QandA.pdf?ver=2020-07-15-161110-867) but do not know how to appropriately and thoroughly proceed on this item yet.

## 3. Inclusion Criteria
- **A**. Must be a part of one or more of the following small business socioeconomic categories:
  - Service-Disabled Veteran-Owned Small Business (SDVOSB),
  - Woman-Owned Small Business (WOSB),
  - Historically Underutilized Business Zones (HUBZone), and/or
  - 8(a)
- **B**. NAICS code(s)
  - **541512**: Computer Systems Design Services
  - 518210
  - 541511
  - 541513
  - 541519
- **C**. Systems, Certifications, Clearances
  - CMMI ≥ ML2
  - ISO 9001:2015, 20000:2018, 27001:2018
  - Earned Value Management System (EVMS)? (Yes/No/Maybe)
  - Acceptable Estimating System (Yes/No/Maybe)
  - Approved Purchasing System (Yes/No/Maybe)
  - Facility Clearance Level (Secret/Top Secret)

## 4. Order of Operations
- **1**. List of all companies that are Small Businesses in the USA by NAICS 541512 from SAM.gov. This list will be called "SAM_SMALL_BUSINESS_541512". This is the same list as [CIO SP4 Approach](https://github.com/ericaosta/alagant/blob/main/cio-sp4/ciosp4_approach.md). 
- **2**. Match SAM_SMALL_BUSINESS to with Awards from USAspending.gov FY08-21. The resulting matched list will be called "MATCHED_SAM_AWARD_541512".
  - Match by recipient_parent_duns
- **3**. Select the following columns from MATCHED_SAM_AWARD_541512:
  - contract_award_unique_key 
  - award_id_piid 
  - parent_award_agency_id
  - parent_award_agency_name
  - parent_award_id_piid
  - total_dollars_obligated
  - current_total_value_of_award
  - action_date_fiscal_year
  - period_of_performance_start_date
  - period_of_performance_current_end_date
  - **cage_code**
  - **recipient_parent_duns**
  - **recipient_parent_name**
  - recipient_country_name
  - recipient_address_line_1
  - recipient_address_line_2
  - recipient_city_name
  - recipient_state_name
  - **recipient_zip_4_code**
  - recipient_phone_number
  - **naics_code**
  - naics_description
  - **service_disabled_veteran_owned_business**
  - **women_owned_small_business**
  - **c8a_program_participant**
  - **historically_underutilized_business_zone_hubzone_firm** 
  - **sba_certified_8a_joint_venture**
  - **SDVOSB**
- **4**. Match MATCHED_SAM_AWARD_541512 to CMMI_SAM, a list of US companies registered with SAM and their corresponding CMMI-SVC or -DEV maturity level (ML)." The resulting list will be called "CMMI_SAM_AWARD_541512."
  - Match by recipient_parent_duns
- **5**. From CMMI_SAM_AWARD_541512, filter companies with keyword matches for FCL, Cost Accounting System, Approved Purchasing System)
  - Search keywords under award_description
- **6.** If list is reasonably short, manually verify CMMI status, and manually check ISO 9001:2015, 20000:2018, and/or 27001:2018
  - Search on company website

##. Algorithms and Code

# Contract Team Arrangements (CTA) Member Search
## 1. Objective
Search will be focused on Relevant Experience and Past Performance.

## 2. Input Data
- Same as *Team Lead Search* 

## 3. Inclusion Criteria
- **A**. Must be a part of one or more of the following small business socioeconomic categories:
  - Service-Disabled Veteran-Owned Small Business (SDVOSB),
  - Woman-Owned Small Business (WOSB),
  - Historically Underutilized Business Zones (HUBZone), and/or
  - 8(a)
- **B**. NAICS code(s)
  - **541512**: Computer Systems Design Services
  - 518210
  - 541511
  - 541513
  - 541519
- **C**. Systems, Certifications, Clearances
  - CMMI ≥ ML2
  - ISO 9001:2015, 20000:2018, 27001:2018
  - Earned Value Management System (EVMS)? (Yes/No/Maybe)
  - Acceptable Estimating System (Yes/No/Maybe)
  - Approved Purchasing System (Yes/No/Maybe)
  - Facility Clearance Level (Secret/Top Secret)
- **E**. Relevant Experience
  - See details on algorithms for [Sectiosn L and M](https://github.com/ericaosta/alagant/blob/main/polaris/polaris_other.md)
- **F**. Past Experience
  - See details on algorithms for [Sectiosn L and M](https://github.com/ericaosta/alagant/blob/main/polaris/polaris_other.md)
## 4. Order of Operations
- TBD

## 5. Algorithms and Code
- [Section C](https://github.com/ericaosta/alagant/blob/main/polaris/polaris_c_algorithm.txt).
- [Sectiosn L and M](https://github.com/ericaosta/alagant/blob/main/polaris/polaris_other.md)
