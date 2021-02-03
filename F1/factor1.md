# Outline
- A. [Criteria](https://github.com/ericaosta/alagant/blob/main/factor1.md#a-criteria)
  - 1 [Capability Maturity Model Integration (CMMI) Level 3](https://github.com/ericaosta/alagant/blob/main/factor1.md#1-capability-maturity-model-integration-cmmi-level-3)
    - 1.1 [Web scraping and data cleaning](https://github.com/ericaosta/alagant/blob/main/factor1.md#11-web-scraping-and-data-cleaning)
    - 1.2 [Assign SAM status, CMMI level, and other data cleaning](https://github.com/ericaosta/alagant/blob/main/factor1.md#12-assign-sam-status-cmmi-level-and-other-data-cleaning)
    - 1.3 [Select companies with >= ML3 and with SAM](https://github.com/ericaosta/alagant/blob/main/factor1.md#13-select--companies-with--ml3-and-with-sam)
    - [Output](https://github.com/ericaosta/alagant/blob/main/factor1.md#output-for-criterion-1)
  - 2 [International Organization for Standardization (ISO) 9001:2015](https://github.com/ericaosta/alagant/blob/main/factor1.md#2-international-organization-for-standardization-iso-90012015)
  - 3 [CSP and Key Technology Partnerships](https://github.com/ericaosta/alagant/blob/main/factor1.md#3-csp-and-key-technology-partnerships)
  - 4 [Demonstrate Experience with at Least Three (3) Projects Implementing and Upgrading Oracle Federal Financials](https://github.com/ericaosta/alagant/blob/main/factor1.md#4-demonstrate-experience-with-at-least-three-3-projects-implementing-and-upgrading-oracle-federal-financials)
    - 4.1 [Clean award data](https://github.com/ericaosta/alagant/blob/main/factor1.md#41-clean-award-data)
    - 4.2 [Create a list of DUNS per company](https://github.com/ericaosta/alagant/blob/main/factor1.md#42-create-a-list-of-duns-per-company)
    - 4.3 [Clean company names with regular expressions](https://github.com/ericaosta/alagant/blob/main/factor1.md#43-clean-company-names-with-regular-expressions)
    - 4.4 [Search for "UFMS" and "ORACLE FINANCIAL" patterns in award descriptions](https://github.com/ericaosta/alagant/blob/main/factor1.md#44-search-for-ufms-and-oracle-financial-patterns-in-award-descriptions)
    - [Output](https://github.com/ericaosta/alagant/blob/main/factor1.md#output-for-criterion-4)
  - 5 [Demonstrate Experience with at Least Two (2) Projects Leading Supporting Cloud Migration/Transformation](https://github.com/ericaosta/alagant/blob/main/factor1.md#5-demonstrate-experience-with-at-least-two-2-projects-leading-supporting-cloud-migrationtransformation)
    - 5.1 [Search for "CLOUD" patterns in award descriptions](https://github.com/ericaosta/alagant/blob/main/factor1.md#51-search-for-cloud-patterns-in-award-descriptions)
    - 5.2 [Search for "MIGRAT" and "TRANSFO" patterns in award descriptions within "CLOUD"](https://github.com/ericaosta/alagant/blob/main/factor1.md#search-for-migrat-and-transfo-patterns-in-award-descriptions-within-cloud) 
    - [Output](https://github.com/ericaosta/alagant/blob/main/factor1.md#output-for-criterion-5)
  - 6 [Demonstrate Experience with at Least Two (2) or More FedRAMP Operational Expertise](https://github.com/ericaosta/alagant/blob/main/factor1.md#6-demonstrate-experience-with-at-least-two-2-or-more-fedramp-operational-expertise)
- B. [Integration of Multiple Criteria](https://github.com/ericaosta/alagant/blob/main/factor1.md#b-integration-of-multiple-criteria)
  - 1 [Match CMMI data to award data](https://github.com/ericaosta/alagant/blob/main/factor1.md#1-match-cmmi-data-to-award-data)
    - 1.1 [Prepare environment](https://github.com/ericaosta/alagant/blob/main/factor1.md#11-prepare-environment)
    - 1.2 [Clean CMMI company names with regular expressions](https://github.com/ericaosta/alagant/blob/main/factor1.md#12-clean-cmmi-company-names-with-regular-expressions)
    - 1.3 [Join CCMI data to DUNS to assign DUNS to CMMI-filtered companies](https://github.com/ericaosta/alagant/blob/main/factor1.md#13-join-ccmi-data-to-duns-to-assign-duns-to-cmmi-filtered-companies)
    - 1.4 [Join CMMI data to awards data by DUNS](https://github.com/ericaosta/alagant/blob/main/factor1.md#14-join-cmmi-data-to-awards-data-by-duns)
  - 2 [Match CMMI data with output for #4 and/or output for #5](https://github.com/ericaosta/alagant/blob/main/factor1.md#2-match-cmmi-data-with-output-for-4-andor-output-for-5)
    - 2.1 [Match CMMI data with output for #4](https://github.com/ericaosta/alagant/blob/main/factor1.md#21-match-cmmi-data-with-output-for-4)
    - 2.2 [Match CMMI data with output for #5](https://github.com/ericaosta/alagant/blob/main/factor1.md#22-match-cmmi-data-with-output-for-5)
  - 3 [Match SAM data and award data and matching with other criteria](https://github.com/ericaosta/alagant/blob/main/factor1.md#3-match-sam-data-and-award-data-and-matching-with-other-criteria)
    - 3.1 [Clean SAM data](https://github.com/ericaosta/alagant/blob/main/factor1.md#31-clean-sam-data)
    - 3.2 [Match SAM status to data from output #4 and #5](https://github.com/ericaosta/alagant/blob/main/factor1.md#32-match-sam-status-to-output-from-output-4-and-5)
- C. [Analysis](https://github.com/ericaosta/alagant/blob/main/factor1.md#c-analysis)
  - 1 [Relationship between CMMI level and ISO 9001:2015](https://github.com/ericaosta/alagant/blob/main/factor1.md#1-relationship-between-cmmi-level-and-iso-90012015)
  - 2 [Relationship between companies with CMMI ML3 or higher and NAICS](https://github.com/ericaosta/alagant/blob/main/factor1.md#2-relationship-between-companies-with-cmmi-ml3-or-higher-and-naics)
  - 3 [Relationship between keywords in award descriptions and NAICS](https://github.com/ericaosta/alagant/blob/main/factor1.md#3-relationship-between-keywords-in-award-descriptions-and-naics)
- D. [Next steps](https://github.com/ericaosta/alagant/blob/main/factor1.md#d-next-steps)

# A. Criteria

### Load packages
```{r }
library(rvest)
library(pander)
library(xml2)
library(tidyverse)
library(dplyr)
```

## 1. Capability Maturity Model Integration (CMMI) Level 3

### 1.1 Web scraping and data cleaning

Access  [CMMI Institute, Published Appraisal Results](https://cmmiinstitute.com/pars/?StateId=c2c50afd-1884-4a85-9665-57d0a50a0e1c&PageNumber=1&Handler=ApplyFilters) and scrape pages 1 through 1913 that correspond to all appraisals published to-date. 

```{r }
# Scrape whole item-card data from all pages; separate into 500 pages at the time so code runs faster
itemcard_1_500 <- lapply(paste0('https://cmmiinstitute.com/pars/?StateId=33296d0d-c5c5-4d47-b36b-c692d73a5ab7&PageNumber=', 1:500),
                function(url){
                  url %>% read_html() %>% 
                    html_nodes("div.item-card") %>% 
                    html_text()
                })

itemcard_501_1000 <- lapply(paste0('https://cmmiinstitute.com/pars/?StateId=33296d0d-c5c5-4d47-b36b-c692d73a5ab7&PageNumber=', 501:1000),
                function(url){
                  url %>% read_html() %>% 
                    html_nodes("div.item-card") %>% 
                    html_text()
                })

itemcard_1001_1500 <- lapply(paste0('https://cmmiinstitute.com/pars/?StateId=33296d0d-c5c5-4d47-b36b-c692d73a5ab7&PageNumber=', 1001:1500),
                function(url){
                  url %>% read_html() %>% 
                    html_nodes("div.item-card") %>% 
                    html_text()
                })

itemcard_1500_1913 <- lapply(paste0('https://cmmiinstitute.com/pars/?StateId=33296d0d-c5c5-4d47-b36b-c692d73a5ab7&PageNumber=', 1501:1913),
                function(url){
                  url %>% read_html() %>% 
                    html_nodes("div.item-card") %>% 
                    html_text()
                })

# turn lists into dfs
df_1_500 <- as.data.frame(do.call(rbind, lapply(itemcard_1_500, as.data.frame)))
df_501_1000 <- as.data.frame(do.call(rbind, lapply(itemcard_501_1000, as.data.frame)))
df_1001_1500 <- as.data.frame(do.call(rbind, lapply(itemcard_1001_1500, as.data.frame)))
df_1501_1913 <- as.data.frame(do.call(rbind, lapply(itemcard_1500_1913, as.data.frame)))

# bind dfs consecutively by rows
df_1_1000 <- rbind(df_1_500, df_501_1000)
df_1_1500 <- rbind(df_1_1000, df_1001_1500)
df_1_1913 <- rbind(df_1_1500, df_1501_1913)

# remove unnecesary dfs thereafter
rm(df_1_500)
rm(df_501_1000)
rm(df_1001_1500)
rm(df_1501_1913)
rm(df_1_1000)
rm(df_1_1500)

# work with df_1_1913

df <- df_1_1913

# remove repeating "[\r\n]" character
orgs1 <- trimws(gsub("[\r\n]", "", df$`X[[i]]`))
df$`X[[i]]` <- orgs1
colnames(df) <- "x"

# separate organization/company name from the rest of the text per row entry
df1 <- df %>% separate(
  col = x,
  into = c("org", "id_level"),
  sep = ":",
  remove = TRUE,
  convert = FALSE,
  extra = "warn",
  fill = "warn"
)
```


### 1.2 Assign SAM status, CMMI level, and other data cleaning
Search for "with SAM" or "without SAM" from each company entry and create a new column that designates the "SAM status" of the company. Repeat for ML2-5 to designate "CMMI level".

```{r}
# separate out SAM, levels, etc.
df1$sam_status <- ifelse(grepl("with SAM",df1$id_level),'with SAM',
                         ifelse(grepl("without SAM", df1$id_level), 'without SAM', 'something_else'))

df1$level_status <- ifelse(grepl("ML3",df1$id_level),'ML3',
                           ifelse(grepl("ML2",df1$id_level),'ML2',
                                  ifelse(grepl("ML5",df1$id_level),'ML5',
                                         ifelse(grepl("ML4",df1$id_level),'ML4', 'something_else'))))

# remove out "ID" from org name
df2 <- df1 %>% separate(
  col = org,
  into = c("org", "null"),
  sep = "ID",
  remove = TRUE,
  convert = FALSE,
  extra = "warn",
  fill = "warn"
)

df2$null <- NULL

# add CMMI-SVC or -DEV; may not be needed
df2$cmmi_type <- ifelse(grepl("CMMI-SVC",df2$id_level),'CMMI-SVC',
                         ifelse(grepl("CMMI-DEV", df2$id_level), 'CMMI-DEV', 'something_else'))

df2 <- df2[-1369,] # weird company, no relevant data

# fix ids to add; not necessary right now
df2$id <- trimws(df2$id)
id_extracted <- str_extract_all(df2$id, "0.|1.|2.|3.|4.|5.|6.|7.|8.|9.")
id_str <- trimws(id$id)
df2$id_ex <- id_ex
id_ex_v2 <- trimws(gsub("#first term ends in space, . , or - ", "", df2$id_ex))


# create a new df with company name, sam status, cmmi level, and cmmi type
cmmi <- df2 %>% select(org, sam_status, level_status, cmmi_type)
```


### 1.3 Select  companies with >= ML3 and with SAM
```{r}
# select SAM with >= ML3
cmmi_sam_ml3 <- cmmi %>% filter(grepl("with SAM", cmmi$sam_status), grepl(c("ML3"), cmmi$level_status))
cmmi_sam_ml4 <- cmmi %>% filter(grepl("with SAM", cmmi$sam_status), grepl(c("ML4"), cmmi$level_status))
cmmi_sam_ml5 <- cmmi %>% filter(grepl("with SAM", cmmi$sam_status), grepl(c("ML5"), cmmi$level_status))

cmmi_final <- rbind(cmmi_sam_ml3, cmmi_sam_ml4, cmmi_sam_ml5)

# export to Excel
library(writexl)
write_xlsx(cmmi_final, "cmmi_2021_sam_ML3_ML4_ML5_world.xlsx")
```
### Output for Criterion #1:
[CMMI ML3-5](https://github.com/ericaosta/alagant/blob/main/cmmi_2021_sam_ML3_ML4_ML5_world.xlsx)

## 2. International Organization for Standardization (ISO) 9001:2015
- I have yet to find a reliable database for companies with ISO certification status. Hoshang has yet to deliver. 
- I manually collected ISO 9001:2015 status from websites from companies that met the CMMI criterion. Please see the data [here](https://github.com/ericaosta/alagant/blob/main/cmmi_with_iso_status.xlsx). Please note that some websites may have a certification but may not show it on their website. 
-  Companies that meet criteria [#4](https://github.com/ericaosta/alagant/blob/main/factor1.md#4-demonstrate-experience-with-at-least-three-3-projects-implementing-and-upgrading-oracle-federal-financials) and/or [#5](https://github.com/ericaosta/alagant/blob/main/factor1.md#5-demonstrate-experience-with-at-least-two-2-projects-leading-supporting-cloud-migrationtransformation) can give us are more likely to be ISO 9001 certified. 

## 3. CSP and Key Technology Partnerships
- I will contact AWS, Oracle, Azure. 
- I manually collected CSPs from websites from companies that met the CMMI criterion. Please see the data [here](https://github.com/ericaosta/alagant/blob/main/cmmi_with_iso_status.xlsx). Please note that some websites may have a partnership but may not show details on their website. 
- Criteria [#4](https://github.com/ericaosta/alagant/blob/main/factor1.md#4-demonstrate-experience-with-at-least-three-3-projects-implementing-and-upgrading-oracle-federal-financials) and/or [#5](https://github.com/ericaosta/alagant/blob/main/factor1.md#5-demonstrate-experience-with-at-least-two-2-projects-leading-supporting-cloud-migrationtransformation) can give us leads for companies that meet this criterion. 

## 4. Demonstrate Experience with at Least Three (3) Projects Implementing and Upgrading Oracle Federal Financials

### 4.1 Clean award data
Reduce dimentionality of awards data ("awards_fy21") from >200 columns to name of company, DUNS, award description, NAICS, CAGE, and country of company. Depending on the objectively, other columns will be selected accordingly. **IMPORTANT**: Please note that this code and subsequent analysis uses *ONLY* award data from fiscal year 2021 as a proof-of-concept. A more thorough analysis will require the aggregate data from FY18-current. 

```{r}
# Read csv file with awards data from FY21; plan to directly unzip and load from url in the future. 
url_awards_fy21 <- "https://files.usaspending.gov/generated_downloads/PrimeAwardSummariesAndSubawards_2021-01-14_H05M14S15472571.zip"
download.file(url_awards_fy21, "awards_fy21.zip")
unzip("awards_fy21.zip")
awards_fy21 <- read_csv("Contracts_PrimeAwardSummaries_2021-01-14_H05M14S17_1.csv")

# Original file has >200 columns. Select 'recipient_name', 'award description', 'recipient_duns', 'naics_code', 'naics_description', 'cage_code', 'recipient_parent_name', 'recipient_parent_duns', 'recipient_country_name' columns to simplify straightforward analysis
awards_fy21_select <- awards_fy21  %>%
   dplyr::select(recipient_name, award_description, recipient_duns, naics_code, naics_description, cage_code, recipient_parent_name, recipient_parent_duns, recipient_country_name)
```

### 4.2 Create a list of DUNS per company 
A list of company names with their corresponding DUNS will be used to join other large sets of data by their company name/DUNS. For instance, the list of CMMI-filtered companies will be joined to with the DUNS list to then further join it to other information (e.g., NAICS, award description, etc.) by their common DUNS/company names. To see an example, please go to [Integration of Multiple Criteria](https://github.com/ericaosta/alagant/blob/main/factor1.md#b-integration-of-multiple-criteria)
```{r}
# Remove duplicate DUNS so there is only one duns per company. In the future, will repeat for fy20-18, merge dataframes by rows, remove duplicates again; assumes duns per company stay the same over time
duns_fy21 <- awards_fy21_select[!duplicated(awards_fy21_select$recipient_duns),] %>%
  select(recipient_duns, naics_code, recipient_name, cage_code, recipient_country_name)

# Select only companies in USA
duns_fy21_usa <- duns_fy21 %>%
  dplyr::filter(recipient_country_name == "UNITED STATES")

# Save xlsx file with list of companies and corresponding DUNS and other ID info for FY2021
write_xlsx(duns_fy21_usa, "duns_FY21_USA.xlsx")
```
### 4.3 Clean company names with regular expressions
Regular expressions ("regex") can "standarize" a pattern between company names. It is important to standarize company names because some website that we will scrap may have company names but not DUNS. Therefore, we can use this tool to analyze government data (e.g., sam.gov, usaspending.gov with other sites, such as cmmiinstitute.com, where we can find companies and their CMMI Level status). 

```{r}
# working list of regex to standarize company names
to_remove <- c("\\LLC$",
               "\\, LLC$", 
               "\\. Inc.$\\", 
               "\\. Inc.$", 
               "\\ INC$", 
               "\\Inc$", 
               "\\Co.$", 
               "\\INC.$", 
               "\\, INC$",
               "\\, INC.$",
               "\\, Inc$",
               "\\, Inc.$",
               "\\L.L.C.$", 
               "\\, L.L.C.$",
               "\\Corp.$", 
               "\\Ltd.$",
               "\\LLC.$",
               "\\L.LC.$",
               "\\, L.LC$",
               "\\L.C.$",
               "\\Llc$",
               "\\PLLC$",
               "\\inc$",
               "\\, Ltd.$",
               "\\.$",
               "\\,$",
               "\\, Llc$",
               "\\, PLLC$",
               "\\#1$",
               "\\Co$",
               "\\Corp$",
               "\\Corporation$",
               "\\CORPORATION$",
               "\\Incorporated$",
               "\\LLP$",
               "\\CORP.$",
               "\\, L L C$",
               "\\CORP$",
               "\\, inc$",
               "\\LLLP$",
               "\\(INC)$",
               "\\, L.L.L.P$",
               "\\ LP$",
               "\\ PC$",
               " P.C$",
               "\\LTD$",
               "\\, LTD$"
               )

# standarize company names by removing regex. Note post second-to-last Co. or Corp. will missout companies with names that have Cor|Corp in main name (e.g., TraCorp)
duns_fy21_usa$x <- gsub(paste(to_remove,collapse="|"),"",duns_fy21_usa$recipient_name) # removes regex
duns_fy21_usa$x <- gsub("TECHNOLOGY|TECHNOLOGIES","TECH",as.character(duns_fy21_usa$x)) # converts "technology'ies' to "tech"
duns_fy21_usa$x <- gsub("COMPANIES|COMPANY","CO",as.character(duns_fy21_usa$x)) # converts "company'ies' to "co"
duns_fy21_usa$y <- gsub(paste(to_remove,collapse="|"),"",duns_fy21_usa$x) # to remove second-to-last terms, such as "Co" before "Inc" in "Co, Inc" and all iterations thereof. 
```

### 4.4 Search for "UFMS" and "ORACLE FINANCIAL" patterns in award descriptions
Text

```{r}
# Select key words "ufms" and "oracle financial" in award descriptions
award_terms$ufms_status <- ifelse(grepl("ufms",awards_fy21_select$award_description),'ufms',
                                  ifelse(grepl("UFMS", awards_fy21_select$award_description), 'ufms', 
                                         ifelse(grepl("ORACLE FINANCIAL", awards_fy21_select$award_description), 'ufms', 'something_else')))
                                         
# Select only companies with awards found to have "ufms" positive status in USA
award_ufms_usa <- award_terms %>%
  dplyr::filter(ufms_status == "ufms", recipient_country_name == "UNITED STATES")

# Select companies with at least 3 awards/projects involving UFMS, Oracle Financial, etc. 
award_ufms_usa_3 <- award_ufms_usa %>%
  dplyr::count(recipient_duns) %>%
  dplyr::filter(n >= 3) %>%
  dplyr::inner_join(award_ufms_usa, by="recipient_duns")

award_ufms_usa_3 <- award_ufms_usa_3[!duplicated(award_ufms_usa_3$recipient_duns),]

# Export data to Excel
write_xlsx(award_ufms_usa_3, "award_ufms_usa_3.xlsx")
```
### Output for Criterion #4:
[Companies with at least 3 projects involving Oracle Federal Financials](https://github.com/ericaosta/alagant/blob/main/award_ufms_usa_3.xlsx)

Company | DUNS | Awards | NAICS code | NAICS description | Award description
--------|------|------------------|------------|-------------------|------------------
CGI FEDERAL INC. | 145969783 | 10 | 541519 | OTHER COMPUTER RELATED SERVICES | BOP UFMS WAVE V - PHASE 2 MIGRATION
INTEGRATED MEDICAL SOLUTIONS, INC | 841580934 | 6 | 621399 | OFFICES OF ALL OTHER MISCELLANEOUS HEALTH PRACTITIONERS | COMPREHENSIVE MEDICAL SERVICES FOR FCI AND UFMS INMATES

> [CGI FEDERAL INC.](https://www.cgi.com/us/en-us/federal/about-cgi-federal) is CMMI-SVC ML3 and ISO 9001:2015 certified. Therefore, the best approach is to start with the most stringent criteria first. The likelihood of meeting more basic criteria (e.g., CMMI Level 3 and up, ISO 9001:2015) increases when more stringent criteria (UFMS, Oracle Financials, etc.) are met. 


## 5. Demonstrate Experience with at Least Two (2) Projects Leading Supporting Cloud Migration/Transformation

### 5.1 Search for "CLOUD" patterns in award descriptions
```{r}
award_terms <- awards_fy21_select

# CLOUD
award_terms$cloud_status <- ifelse(grepl("cloud",awards_fy21_select$award_description),'cloud',
                         ifelse(grepl("CLOUD", awards_fy21_select$award_description), 'cloud', 'something_else'))

award_cloud_usa <- award_terms %>%
  dplyr::filter(cloud_status == "cloud", recipient_country_name == "UNITED STATES")
```
> Note: Awards containing the word "cloud" are more likely to have NAICS related to "OTHER COMPUTER RELATED SERVICES" and code 541519. 


###  5.2 Search for "MIGRAT" and "TRANSFO" patterns in award descriptions within "CLOUD"
Search for words containing "migrat" and "transfo" within the "cloud"-containing awards and create a new column that designates the "migration" or "transformation" status of the award description. 

```{r}
## CLOUD::MIGRAT and ::TRANSFORMATION
award_cloud_usa$migration_status <- ifelse(grepl("migrat",award_cloud_usa$award_description),'migration',
                         ifelse(grepl("MIGRAT", award_cloud_usa$award_description), 'migration', 'something_else'))

award_cloud_usa$transformation_status <- ifelse(grepl("transfo",award_cloud_usa$award_description),'transformation',
                         ifelse(grepl("TRANSFO", award_cloud_usa$award_description), 'transformation', 'something_else'))

# Select awards that contain the words "migration" or "transformation"
award_cloud_migration <- award_cloud_usa %>%
  dplyr::filter(migration_status == "migration")

award_cloud_transformation <- award_cloud_usa %>%
  dplyr::filter(transformation_status == "transformation")

# Combine both "migration" and "transformation" hits
award_cloud_migration_transformation <- rbind(award_cloud_migration, award_cloud_transformation)

# At least 2 awards/projects involving cloud migration/transformation
award_cloud_migration_transformation_2 <- award_cloud_migration_transformation %>%
   dplyr::count(recipient_duns) %>%
  dplyr::filter(n >= 2) %>%
  dplyr::inner_join(award_cloud_migration_transformation, by="recipient_duns")

award_cloud_migration_transformation_2 <- award_cloud_migration_transformation_2[!duplicated(award_cloud_migration_transformation_2$recipient_duns),]

# Export to Excel
write_xlsx(award_cloud_migration_transformation_2, "award_cloud_migration_transformation_2.xlsx")
```
### Output for Criterion #5:
[Companies with at least 2 projects involving Cloud Migration and Transformation](https://github.com/ericaosta/alagant/blob/main/award_cloud_migration_transformation_2.xlsx)

Company | DUNS | Awards | NAICS code | NAICS description | Award description
--------|------|------------------|------------|-------------------|------------------
BUSINESS INFORMATION TECHNOLOGY SOLUTIONS LLC | 169939688 | 3 | 541512 | COMPUTER SYSTEMS DESIGN SERVICES | CLOUD OPERATIONS AND MIGRATION SERVICES - FUNDING MOD

> [BUSINESS INFORMATION TECHNOLOGY SOLUTIONS LLC](https://cognosante.com/our-company/certifications-contract-vehicles/) is CMMI-SVC ML3 and ISO 9001:2015 certified. Therefore, the best approach is to start with the most stringent criteria first. The likelihood of meeting more basic criteria (e.g., CMMI Level 3 and up, ISO 9001:2015) increases when more stringent criteria (cloud migration/transformation, etc.) are met.  

## 6. Demonstrate Experience with at Least Two (2) or More FedRAMP Operational Expertise
Most of these companies will already have this experience. 

# B. Integration of Multiple Criteria

## 1. Match CMMI data to award data

### 1.1 Prepare environment
```{r }
# Read xlsl file with cmmi data
cmmi <- read_excel("cmmi_2021_sam_ML3_ML4_ML5_world.xlsx")

# Country names for companies from CMMI list; had to be manually collected as a proof-of-concept for future analyses
country <- list(
  "AASKI Technologies (A Mag Aerospace Company)" = "USA", 
  "Adams Communication & Engineering Technology, Inc."= "USA",
  "Aselsan MGEO(Aselsan MGEO)" = "Turkey",
  "Avante Codeworx Private Limited" = "India",
  "Axle Informatics, LLC" = "USA",
  "BAE Systems Electronic Systems" = "USA, UK, Canada, Israel",
  "Boeing India Private Limited (English)" = "India",
  "Centauri" = "USA",
  "Changeis, Inc." = "USA",
  "China Eastern Airlines Corporation Limited" = "China",
  "China Post Information Technology" = "China",
  "Client Network Services India Pvt Ltd" = "USA, India",
  "Cole Engineering Services, Inc." = "USA",
  "CompQsoft, Inc." = "USA",
  "Concentrix Services Pvt. Ltd." = "USA, India",
  "Dovel Technologies, LLC" = "USA",
  "Dynamik Technologies Sdn Bhd" = "Brunei",
  "Earth Resources Technology, Inc. (ERT)" = "USA",
  "ECS Federal, LLC" = "USA",
  "Efftronics Systems Private Limited" = "India",
  "ESEN SYSTEMS INTEGRATION" = "Turkey",
  "Evergrande life insurance Co., Ltd." = "China",
  "Evolver Inc." = "USA",
  "Guangdong Oriental Thought Co., Ltd." = "China",
  "Highlight Technologies, LLC." = "USA",
  "Holostik India Limited" = "India",
  "Housing & Development Board (HDB)" = "Singapure",
  "IEM" = "USA",
  "IERUS Technologies, Inc." = "USA",
  "Indra Sistemas S.A." = "USA, Spain, others", 
  "Industrias Lior S.A. de C.V." = "Mexico",
  "Info Gain Consulting LLC" = "USA", 
  "Inserso Corporation" = "USA",
  "Integra Micro Software Services Private Limited" = "India, USA, Singapore",
  "Invictus International Consulting" = "USA",
  "Ison Technologies Private Limited" = "India",
  "JYG Innovations, LLC." = "USA", 
  "KPMG Advisory Services Private Limited" = "India",
  "Leonardo DRS" = "USA",
  "Mercer Engineering Research Center (MERC)" = "USA",
  "Metis Technology Solutions, Inc." = "USA",
  "MicroGenesis Techsoft Pvt Ltd" = "India",
  "Next Tier Concepts, Inc." = "USA",
  "Nextchip Co.,Ltd." = "Korea",
  "Primestone S.A.S.(Primestone S.A.S.)" = "USA",
  "Pumex Computing, LLC." = "USA",
  "QA InfoTech Software Services Private Limited" = "India, USA, Canada",
  "Quality Innovation, Inc." = "USA",
  "RiVi Consulting Group LLC" = "USA, India",
  "Ryan Consulting Group" = "USA",
  "Samin TekMindz India Private Limited" = "India",
  "Sansec Technology Co., Ltd." = "China",
  "SEV1Tech LLC" = "USA",
  "SICPA S.A." = "Switzerland",
  "Southwest Research Institute" = "USA",
  "SVAM International Incorporated" = "USA, Mexico, India",
  "Swain Techs" = "USA",
  "Technica Corporation" = "USA",
  "Teradyne" = "USA",
  "Trigent Solutions Inc." = "USA",
  "UNISYS, S. L. U." = "USA, Spain",
  "VariQ Corporation" = "USA",
  "Vectrus Mission Solutions Corporation" = "USA",
  "Aderas, Inc." = "USA",
  "Alion Science and Technology Corporation" = "USA",
  "Unisoc (Shanghai) Technologies Co., Ltd" = "China",
  "Beijing Join-Cheer Government Software Co., Ltd." = "China",
  "Beijing Join-Cheer Software Co., LTD." = "China",
  "Beijing Sifang Automation Co., Ltd." = "China",
  "Beijing Sifang Engineering Co., Ltd." = "China",
  "China Telecom System Integration Co., Ltd" = "China",
  "General Atomics Aeronautical Systems Inc." = "USA",
  "Hanwha Systems" = "Korea",
  "Hewlett Packard Enterprise Co., Ltd." = "China, others",
  "MAXIMUS Federal Services" = "USA",
  "National Government Services, Inc." = "USA",
  "Riptide Software Inc." = "USA",
  "SoftManagement S.A." = "Colombia",
  "Tata Consultancy Services Limited" = "India",
  "Wipro Limited" = "India",
  "Yash Technologies Pvt. Ltd." = "USA")
```

### 1.2 Clean CMMI company names with regular expressions
```{r}
# Regular expression to standardize company names from CMMI website; just a few more additions to "to_remove" as in A 4.4
to_remove_cmmi <- c("\\LLC$",
               "\\, LLC$", 
               "\\. Inc.$\\", 
               "\\. Inc.$", 
               "\\ INC$", 
               "\\Inc$", 
               "\\Co.$", 
               "\\INC.$", 
               "\\, INC$",
               "\\, INC.$",
               "\\, Inc$",
               "\\, Inc.$",
               "\\L.L.C.$", 
               "\\, L.L.C.$",
               "\\Corp.$", 
               "\\Ltd.$",
               "\\LLC.$",
               "\\L.LC.$",
               "\\, L.LC$",
               "\\L.C.$",
               "\\Llc$",
               "\\PLLC$",
               "\\inc$",
               "\\, Ltd.$",
               "\\.$",
               "\\,$",
               "\\, Llc$",
               "\\, PLLC$",
               "\\#1$",
               "\\Co$",
               "\\Corp$",
               "\\Corporation$",
               "\\CORPORATION$",
               "\\Incorporated$",
               "\\LLP$",
               "\\CORP.$",
               "\\, L L C$",
               "\\CORP$",
               "\\, inc$",
               "\\LLLP$",
               "\\(INC)$",
               "\\, L.L.L.P$",
               "\\ LP$",
               "\\ PC$",
               " P.C$",
               "\\LTD$",
               "\\, LTD$",
               "\\s*\\([^\\)]+\\)",
               "\\Pvt Ltd",
               "\\Pvt.",
               "Private Limited",
               "S.A.$",
               "S.A. de C.V",
               "S. A",
               "Pvt.$",
               "S.A.S",
               "\\, LTD",
               "\\, Ltd",
               "\\Limited$",
               ",.*"
               )

# Standarize company names; use touper() to convert character strings to uppercase
cmmi$x <- gsub(paste(to_remove_cmmi,collapse="|"),"",as.character(cmmi$org))
cmmi$x <- toupper(gsub("Technologies|Technology","Tech",as.character(cmmi$x)))
cmmi$x <- toupper(gsub("Companies|Company","Co",as.character(cmmi$x)))
cmmi$x <- toupper(gsub("BAE SYSTEMS ELECTRONIC SYSTEMS","BAE SYSTEMS INFORMATION AND ELECTRONIC SYSTEMS INTEGRATION ",as.character(cmmi$x))) # a specific modification to a company name
cmmi$y <- toupper(gsub(paste(to_remove_cmmi,collapse="|"),"",as.character(cmmi$x)))

# Select USA-only companies from CMMI list. The 'country' list manually generated after the list of 82-row table of CMMI Level >=3 and SAM+ companies was generated. Next time, I can specific USA-only companies on the CMMI website prior to scraping. 
countries <- as.data.frame(unlist(country)) 
countries$Names <- rownames(countries)
countries$x <- gsub(paste(to_remove_cmmi,collapse="|"),"",as.character(countries$Name))
countries$x <- toupper(gsub("Technologies|Technology","Tech",as.character(countries$x)))
countries$x <- toupper(gsub("Companies|Company","Co",as.character(countries$x)))
countries$x <- toupper(gsub("BAE SYSTEMS ELECTRONIC SYSTEMS","BAE SYSTEMS INFORMATION AND ELECTRONIC SYSTEMS INTEGRATION ",as.character(countries$x)))
countries$y <- toupper(gsub(paste(to_remove_cmmi,collapse="|"),"",as.character(countries$x)))

# Inner join
countries_cmmi <- inner_join(countries, cmmi, by="y", suffix=c("_countries","_cmmi"))
countries_cmmi_anti <- anti_join(countries, cmmi, by="y", suffix=c("_countries","_cmmi"))
countries_select <- countries_cmmi %>%
  filter(`unlist(country)` == "USA") %>%
  select(`unlist(country)`, Names, y, sam_status, level_status)
colnames(countries_select) <- c("country", "Name", "y", "sam_status", "level_status")
```

### 1.3 Join CCMI data to DUNS to assign DUNS to CMMI-filtered companies
```{r}
# Inner join companies from CMMI list ('cmmi') and DUNS list FY21 ('). Each row represents a unique DUNS. It seems like one company can have multiple DUNS. 

# cmmi ML3 >=3 and SAM in USA
cmmi_duns_usa <- inner_join(countries_select, duns_fy21_usa, by="y", suffix=c("_cmmi","_duns")) # matched
anti_cmmi_duns_usa <- anti_join(countries_select, duns_fy21_usa, by="y", suffix=c("_cmmi","_duns")) # unmatched

# There are a total of 27 unique companies from CMMI matched to their DUNS. Success rate of approach = 27/41 = 66% (out of total unique companies from 'countries_select'). Improving the regex and adding DUNS from previous fiscal years could increase the success rate of matching DUNS from usaspending.gov to data from scraped websites such as cmmiinstitute.com
unique(cmmi_duns_usa$Name)
```

### 1.4 Join CMMI data to awards data by DUNS
```{r}
# Award data in USA for companies with CMMI and select only relevant columns, such as award_description, recipient_duns, naics_code, naics_description
cmmi_duns_award <- inner_join(cmmi_duns_usa, awards_fy21_select, by="recipient_duns", suffix = c("_cmmi","_award"))
cmmi_duns_award_select <- dplyr::select(cmmi_duns_award, y, award_description, recipient_duns, naics_code_cmmi, naics_description, sam_status, level_status, cage_code_cmmi)

# Clean column names
colnames(cmmi_duns_award_select) = c("company_name","award_description","recipient_duns","naics_code", "naics_description", "sam_status", "cmmi_level", "cage_code")
```
## 2. Match CMMI data with [output for #4](https://github.com/ericaosta/alagant/blob/main/factor1.md#output-for-criterion-4) and/or [output for #5](https://github.com/ericaosta/alagant/blob/main/factor1.md#output-for-criterion-5)

### 2.1 Match CMMI data with output for #4
```{r}
# join with cmmi 
inner_join(award_ufms_usa_3, cmmi_duns_usa, by="recipient_duns")
```
> No matches were found using this approach. This is *not* accurate. For instance, CGI FEDERAL, INC. reports having a CMMI-SVC ML3 on their website. Therefore, the following need to be addressed: (1) the CMMI Institute website needs to be updated to accurately represent current data, (2) improvement/optimization of regex to standarize company names, and (3) search for other potential and reliable websites to scrape CMMI data.

### 2.2 Match CMMI data with output for #5
```{r}
# join with cmmi 
inner_join(award_cloud_migration_transformation_2, cmmi_duns_usa, by="recipient_duns")
```
> No matches were found using this approach. This is *not* accurate. For instance, BUSINESS INFORMATION TECHNOLOGY SOLUTIONS, LLC. reports having a CMMI-SVC ML3 on their website. Therefore, the following need to be addressed: (1) the CMMI Institute website needs to be updated to accurately represent current data, (2) improvement/optimization of regex to standarize company names, and (3) search for other potential and reliable websites to scrape CMMI data.

## 3. Match SAM data and award data and matching with other criteria 
### 3.1 Clean SAM data
```{r}
# Match SAM data with award data
library(readxl)
sam_companies <- read_excel("https://github.com/ericaosta/alagant/blob/main/company-unique-list.xlsx") # from Andrew
View(sam_companies)

sam_awards_usa <- sam_companies %>%
  select(Name, DUNS, Country) %>%
  filter(Country == "UNITED STATES")

colnames(sam_awards_usa) <- c("recipient_name", "recipient_duns", "recipient_country_name")
sam_awards_usa$recipient_duns <- as.character(sam_awards_usa$recipient_duns)

sam_awards_usa <- sam_awards_usa %>%
  inner_join(awards_select, by="recipient_duns", suffix = c("_sam", "_award")) 

sam_awards_usa <- sam_awards_usa[!duplicated(sam_awards_usa$recipient_duns),] %>%
  dplyr::mutate(sam_status = paste("with SAM")) %>%
  dplyr::select(recipient_name_award, recipient_duns, naics_code_award, naics_description_award, sam_status)
```

### 3.2 Match SAM status to data from output #4 and #5
```{r}
# Crit 4; not successful
sam_award_crit_4 <- award_cloud_migration_transformation_2 %>%
  dplyr::inner_join(sam_awards_usa, by="recipient_duns", suffix = c("_crit4", "_sam"))

# Crit 5; not successful
sam_award_crit_5 <- award_ufms_usa_3 %>%
  dplyr::inner_join(sam_awards_usa, by="recipient_duns", suffix = c("_crit4", "_sam"))
```
> No matches were found using this approach. It is likely due to the *limited award data* (i.e., only working with FY2021). By aggregating award data for FY2018-21, it is likely to get hits for matches. 

# C. Analysis
Corresponding example code for generating plots can be found [here](https://github.com/ericaosta/alagant/blob/main/plots/plots.md).

## 1. Relationship between CMMI level and ISO 9001:2015
- Data were obtained from CMMI as shown in [#1](https://github.com/ericaosta/alagant/blob/main/factor1.md#1-capability-maturity-model-integration-cmmi-level-3). ISO 9001:2015 were obtained by manually extracting data from individual company websites. 
- More companies tend to have CMMI maturity level (ML) 3 than ML4 or ML5. There are more companies with ML5 than ML4. There does not seem to be a trend between CMMI level and ISO 9001:2015 certification status. However, a reliable database for ISO certification is needed to fully support this conclusion. 

### Figure 1. CMMI Levels and ISO 9001:2015 certification status in companies with SAM worldwide.
![cmmi_iso](https://github.com/ericaosta/alagant/blob/main/plots/cmmi_iso.png)

## 2. Relationship between companies with CMMI ML3 or higher and NAICS 
- Data were obtained from CMMI as shown in [#1](https://github.com/ericaosta/alagant/blob/main/factor1.md#1-capability-maturity-model-integration-cmmi-level-3) and awards from FY2021 as shown in [#4](https://github.com/ericaosta/alagant/blob/main/factor1.md#4-demonstrate-experience-with-at-least-three-3-projects-implementing-and-upgrading-oracle-federal-financials).

### Figure 2. Percertage of awards per unique NAICS code per company with CMMI ML3 or higher.
![cmmi_naics_code](https://github.com/ericaosta/alagant/blob/main/plots/cmmi_naics_code.png)
> **Fig. 2** Companies are on the y-axis, % awards/NAICS code on x-axis, legend depicts NAICS code by color, and dashed line depicts the median % awards/NAICS code across all companies. For more information about NAICS codes and descriptions, please visit [NAICS & SIC Identification Tools](https://www.naics.com/search/).

### Figure 3. Percertage of awards per unique NAICS descriptions per company with CMMI ML3 or higher.
![cmmi_naics_description](https://github.com/ericaosta/alagant/blob/main/plots/cmmi_naics_description.png)
> **Fig. 3** Companies are on the y-axis, % awards/NAICS description on x-axis, legend depicts NAICS descriptions by color, and dashed line depicts the median % awards/NAICS code across all companies. For more information about NAICS codes and descriptions, please visit [NAICS & SIC Identification Tools](https://www.naics.com/search/).

## 3. Relationship between keywords in award descriptions and NAICS
- Data were obtained from awards from FY2021 as shown in [#4](https://github.com/ericaosta/alagant/blob/main/factor1.md#4-demonstrate-experience-with-at-least-three-3-projects-implementing-and-upgrading-oracle-federal-financials).

### Figure 4.  Relationship between "UFMS" and "ORACLE FINANCIAL" in award descriptions and NAICS. 
![ufms oracle financials naics](https://github.com/ericaosta/alagant/blob/main/plots/ufms_naics_code.png)
> **Fig. 4** Companies are on the y-axis, % awards/NAICS code on x-axis, legend depicts NAICS code by color, and dashed line depicts the median % awards/NAICS code across all companies. Plot with NAICS descriptions can be found [here](https://github.com/ericaosta/alagant/blob/main/plots/ufms_naics_description.png).

### Figure 5. Relationship between "CLOUD", "MIGRAT" and "TRANSFO" in award descriptions and NAICS. 
![cloud migrat transfo naics](https://github.com/ericaosta/alagant/blob/main/plots/cloud_migration_transformation.png)
> **Fig. 5** Companies are on the y-axis, % awards/NAICS code on x-axis, legend depicts NAICS code by color, and dashed line depicts the median % awards/NAICS code across all companies. They keywords "MIGRAT" and "TRANSFO" were searched in a subset of companies that were all positive for the keyword "CLOUD" in their award desxcriptions. Plot with NAICS descriptions can be found [here](https://github.com/ericaosta/alagant/blob/main/plots/cloud_migration_transformation_description.png).


# D. Next Steps
- Subsetting migrat:transfor in cloud (~ cloud and migrat|transfo) vs. cloud|migrat|transfo to assess sensitivity vs. specificity
- Aggregating award data for FY2018-21 to generate a comprehensive and reliable company-DUNS list and award data.
- Determining a reliable source for companies and their CSPs and ISO certifications
- Optimizing regex to standarize company names
- Simplifying code, writing functions, and creating a package/software for automatization
