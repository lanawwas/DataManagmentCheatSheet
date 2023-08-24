# R and Rstudio installtion in ubuntu 20.04

```bash
```

```bash
```

```bash
```

```bash
```


```bash
```


```bash
```

reference : https://medium.com/sicara/get-started-pyspark-jupyter-guide-tutorial-ae2fe84f594f

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

