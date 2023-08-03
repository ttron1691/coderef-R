# Code Reference for R
## Tidyverse
### Tibble
We can create a tibble by using the following command
```R
df <- tibble(id = c(1, 2, 3),
             name = c("A", "B", "C"),
             age = c(25, 49, 31)) 
```
#### Mutate
In order to create new variables, we can use mutate
```R
df_add_sum <- df %>%
  mutate(sum = a1 + a2)  
```
#### Filter
Filter is used to filter rows based on given conditions
```R
df %>%
  filter(age >= 30)  
```

