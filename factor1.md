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

## 2. International Organization for Standardization (ISO) 9001:2015

I have yet to find a reliable database for companies with ISO certification status. Hoshang has yet to deliver. For now, companies that meet criteria [#4](https://github.com/ericaosta/alagant/blob/main/factor1.md#4-demonstrate-experience-with-at-least-three-3-projects-implementing-and-upgrading-oracle-federal-financials) and/or [#5](https://github.com/ericaosta/alagant/blob/main/factor1.md#5-demonstrate-experience-with-at-least-two-2-projects-leading-supporting-cloud-migrationtransformation) can give us are more likely to be ISO 9001 certified. 

## 3. CSP and Key Technology Partnerships

I will contact AWS, Oracle, Azure. For now, criteria [#4](https://github.com/ericaosta/alagant/blob/main/factor1.md#4-demonstrate-experience-with-at-least-three-3-projects-implementing-and-upgrading-oracle-federal-financials) and/or [#5](https://github.com/ericaosta/alagant/blob/main/factor1.md#5-demonstrate-experience-with-at-least-two-2-projects-leading-supporting-cloud-migrationtransformation) can give us leads for companies that meet this criterium. 

## 4. Demonstrate Experience with at Least Three (3) Projects Implementing and Upgrading Oracle Federal Financials

### 4.1 Clean award data
Reduce dimentionality of awards data ("awards_fy21") from >200 columns to name of company, DUNS, award description, NAICS, CAGE, and country of company. Depending on the objectively, other columns will be selected accordingly. 

```{r}
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
> [CGI FEDERAL INC.](https://www.cgi.com/us/en-us/federal/about-cgi-federal) is CMMI-SVC ML3 and ISO 9001:2015 certified. Therefore, the best approach is to start with the most stringent criteria first. The likelihood of meeting more basic criteria (e.g., CMMI Level 3 and up, ISO 9001:2015) increases when more stringent criteria (UFMS, Oracle Financials, etc.) are met. 


## 5. Demonstrate Experience with at Least Two (2) Projects Leading Supporting Cloud Migration/Transformation

### 5.1 Search for "CLOUD" patterns in award descriptions
Text
```{r}
award_terms <- awards_fy21_select

# CLOUD
award_terms$cloud_status <- ifelse(grepl("cloud",awards_fy21_select$award_description),'cloud',
                         ifelse(grepl("CLOUD", awards_fy21_select$award_description), 'cloud', 'something_else'))

award_cloud_usa <- award_terms %>%
  dplyr::filter(cloud_status == "cloud", recipient_country_name == "UNITED STATES")
```
> Note: Awards containing the word "cloud" are more likely to have NAICS related to "OTHER COMPUTER RELATED SERVICES" and code 541519. 


###  Search for "MIGRAT" and "TRANSFO" patterns in award descriptions within "CLOUD"
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
> [BUSINESS INFORMATION TECHNOLOGY SOLUTIONS LLC](https://cognosante.com/our-company/certifications-contract-vehicles/) is CMMI-SVC ML3 and ISO 9001:2015 certified. Therefore, the best approach is to start with the most stringent criteria first. The likelihood of meeting more basic criteria (e.g., CMMI Level 3 and up, ISO 9001:2015) increases when more stringent criteria (cloud migration/transformation, etc.) are met.  

## 6. Demonstrate Experience with at Least Two (2) or More FedRAMP Operational Expertise

# B. Integration of Multiple Criteria

# C. Analysis


