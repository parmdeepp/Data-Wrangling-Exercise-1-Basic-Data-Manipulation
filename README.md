# Data-Wrangling-Exercise-1-Basic-Data-Manipulation
 refine <- refine %>% mutate(company = ifelse(grepl("^phil|^fil|^phl", company, ignore.case = TRUE), "philips", company)) %>%
+     mutate(company = ifelse(grepl("^ak", company, ignore.case = TRUE), "akzo", company)) %>%
+     mutate(company = ifelse(grepl("^van", company, ignore.case = TRUE), "van_houten", company)) %>%
+     mutate(company = ifelse(grepl("^uni", company, ignore.case = TRUE), "unilever", company))
> refine <- refine %>% separate(`Product code / number`, into=c("product_code", "Product_number"), sep = "-")
> refine <- refine %>% mutate("product_category" = ifelse(product_code == "p", "Smartphone", "")) %>%
+     mutate("product_category" = ifelse(product_code == "x", "Laptop", product_category)) %>%
+     mutate("product_category" = ifelse(product_code == "v", "TV", product_category)) %>%
+     mutate("product_category" = ifelse(product_code == "q", "Tablet", product_category))
> refine <- refine %>% mutate("full_address" = paste(refine$city, refine$country, refine$name, sep = ",") )
> refine <- refine %>% mutate(company_philips = ifelse(company =="philips", 1, 0)) %>%
+     mutate(company_akzo = ifelse(company == "akzo", 1, 0)) %>%
+     mutate(company_van_houten = ifelse(company == "van_houten", 1, 0)) %>%
+     mutate(company_unilever = ifelse(company == "unilever", 1, 0))
> refine <- refine %>% mutate(product_smartphone = ifelse(product_category == "Smartphone", 1, 0)) %>%
+     mutate(product_TV = ifelse(product_category == "TV", 1, 0)) %>%
+     mutate(product_laptop = ifelse(product_category == "Laptop", 1, 0)) %>%
+     mutate(product_tablet = ifelse(product_category == "Tablet", 1, 0))
