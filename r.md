# R and Rstudio installtion in ubuntu 20.04

```bash
sudo apt install r-base
```

```bash
sudo apt install r-cran-rstan r-cran-tidyverse
```

```bash
wget https://download1.rstudio.org/electron/jammy/amd64/rstudio-2023.06.2-561-amd64.deb

```

```bash
sudo apt install -f ./rstudio-2023.06.2-561-amd64.deb
```


```bash
rstudio
```


# rstudio read data from csv file

```r
df <- read.csv("~/path_to_file_.csv")
````

# Show csv schema and explore 

### columns & schema

```r
tibble::glimpse(df)
```
### schema

```r
```

### Summary statistics 

```r
```

### Remove all missing values from dataframe

```r
```
### Remove specific comumns from the dataframe 

```r
df2 <- subset(df, select = -c(?column1, column2,....,columnN))
```

### Filter Operations 

Filter Rows by a column value
```r
filter(df, ?column == '?value')
```

Filter Rows by list of column Values
```r
filter(df, ?column %in% c('?val1','?val2','?val3'))
```
Filter Rows by Checking values on Multiple Columns
```r
filter(df, ?column1 == '?value1' & ?column2 >?value2)
```

Filter DataFrame by column name column2 and column3.
```r
subset(df,?column1 == '?value',select = c('column2','column3'))
```

### Correlation calcualtion and plot 

Install the ggcorrplot package to use for the correlation calculations and plot 
```r
install.packages("ggcorrplot")
```
calculate the correlation and store in cors as a matrix with numbers 
```r
cors <- cor(df, user = "pairwise.complete.obs")
```
store the correlation plot matrix in a gg element 
``


reference: http://fhollenbach.org/OLD_polisci209_DONOTUSE/img/images/notes-18-correlation-r.pdf
# r connect to SQL postgresql

