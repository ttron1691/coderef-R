# Code Reference for R
# Install packages
We can install packages in R via the following command
```R
install.packages('package')
```
## Tidyverse
We load the R-Package for "tidyverse" as follows
```R
library(tidyverse)
```
### Tibble
A tibble, or tbl_df, is a data frame container type which is considered as a modern reimagining of the data.frame. 
We can create a tibble by using the following command
```R
df <- tibble(id = c(1, 2, 3),
             name = c("A", "B", "C"),
             age = c(25, 49, 31)) 
```
This translates to the following tibble
```R
df
# A tibble: 3 × 3
     id name    age
  <dbl> <chr> <dbl>
1     1 A        25
2     2 B        49
3     3 C        31
```
#### Mutate
In order to create new variables, we can use mutate
```R
df_age_double <- df %>%
  mutate(age_double = 2 * age)

df_add_add_flag <- df %>%
  mutate(flag_age_over_30 = ifelse(age > 30, "yes", "no"),
         flag_age_less_50 = case_when(age < 50 ~ TRUE,
                                      TRUE ~ FALSE))  
```
This gives as a result
```R
df_age_double
# A tibble: 3 × 4
     id name    age age_double
  <dbl> <chr> <dbl>      <dbl>
1     1 A        25         50
2     2 B        49         98
3     3 C        31         62
```
#### Filter
Filter is used to filter rows based on given conditions
```R
df_age_filter_30 <- df %>%
  filter(age >= 30)

df_name_filter <- df %>%
  filter(name %in% c("B", "A"))  
```
This results in
```R
# A tibble: 2 × 3
     id name    age
  <dbl> <chr> <dbl>
1     2 B        49
2     3 C        31
```
