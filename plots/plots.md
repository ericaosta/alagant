#  Trends in award descriptions based on NAICS 
```{r}
library(ggplot2)
library(readxl)

cmmi_duns_award_select <- read_excel("cmmi_duns_award_select.xlsx")
```

## NAICS CODE
### Sort, calculate medians, and percentages
```{r}
naics_code_groups <- cmmi_duns_award_select %>%
  dplyr::count(naics_code, company_name, sort=TRUE) %>%
  dplyr::mutate(percentage_naics = signif((n/(sum(n))*100), digits = 2)) %>%
  dplyr::mutate(median = median(n)) %>%
  dplyr::mutate(median_percent = median(percentage_naics)) %>% 
  dplyr::mutate(mean = mean(n)) %>%
  dplyr::mutate(mean_percent = mean(percentage_naics)) %>%
  dplyr::mutate(sd = sd(n)) 

naics_code_groups$median_below_above <- ifelse(naics_code_groups$percentage_naics < 1.703578, "below", "above")
naics_code_groups$`NAICS code` <- as.character(naics_code_groups$naics_code)
```
### Plot
```{r}
ggplot(naics_code_groups, aes(x = reorder(company_name, percentage_naics), y = percentage_naics, label=percentage_naics)) + 
  geom_point(stat='identity', aes(col=`NAICS code`), size=8) +
    geom_text(color="black", size=3) +
  labs(x = "",
       y = "Percentage of awards per NAICS code",
       title="Companies with CMMI ≥ ML3") +
  ylim(0, 15) +
  coord_flip() +
  geom_hline(yintercept=1.7, linetype="dashed", color = "black") +
  annotate("text", y = 3.5, x = 1.5, label= "Median") +
  theme_classic() 
```
### Output:
![CMMI NAICS CODE](https://github.com/ericaosta/alagant/blob/main/plots/cmmi_naics_code.png)


## NAICS DESCRIPTION
### Sort, calculate medians, and percentages

```{r}
naics_description_groups <- cmmi_duns_award_select %>%
  dplyr::count(naics_description, company_name, sort=TRUE) %>%
  dplyr::mutate(percentage_naics = n/(sum(n))*100)

naics_description_groups <- cmmi_duns_award_select %>%
  dplyr::count(naics_description, company_name, sort=TRUE) %>%
  dplyr::mutate(percentage_naics = signif((n/(sum(n))*100), digits = 2)) %>%
  dplyr::mutate(median = median(n)) %>%
  dplyr::mutate(median_percent = median(percentage_naics)) %>% 
  dplyr::mutate(mean = mean(n)) %>%
  dplyr::mutate(mean_percent = mean(percentage_naics)) %>%
  dplyr::mutate(sd = sd(n)) 

naics_description_groups <- naics_description_groups %>%
  dplyr::filter(percentage_naics > 1)

naics_description_groups$`NAICS description` <- as.character(naics_description_groups$naics_description)
```

## Plot
```{r}
ggplot(naics_description_groups, aes(x = reorder(company_name, percentage_naics), y = percentage_naics, label=percentage_naics)) + 
  geom_point(stat='identity', aes(col=`NAICS description`), size=8) +
    geom_text(color="black", size=3) +
  labs(x = "",
       y = "Percentage of awards per NAICS",
       title="Companies with CMMI ≥ ML3") +
  ylim(0, 11) +
  coord_flip() +
  geom_hline(yintercept=0.51, linetype="dashed", color = "black") +
  annotate("text", y = 1, x = 0.55, label= "Median") +
  theme_classic() 
```
### Output:
![CMMI NAICS DESCRIPTION](https://github.com/ericaosta/alagant/blob/main/plots/cmmi_naics_description.png)
