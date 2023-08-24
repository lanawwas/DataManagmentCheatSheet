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

# r connect to SQL postgresql

