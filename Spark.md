# pyspark with jupter installtion

```bash
python -m venv spark
```

```bash
source spark/bin/activate
```

```bash
pip install --upgrade pip 
```

```bash
pip install notebook
```


```bash
pip install pyspark
```


```bash
pip install findspark
```

#pyspark define inside notebook 


```python
import findspark
findspark.init()
import pyspark

from pyspark import SparkContext

sc = SparkContext.getOrCreate()

sqlContext = SQLContext(sc)
```
reference : https://medium.com/sicara/get-started-pyspark-jupyter-guide-tutorial-ae2fe84f594f

# pyspark read data from csv file

```python
df = sqlContext.read.load('file://<?path_to_file_.csv>',
format='com.databricks.spark.csv', header='true', inferSchema='true' )
````

# Show csv schema and explore 

### columns 

```python
df.columns
```
### schema

```python
df.printSchema()
```

### Summary statistics 

```python
df.describe().toPandas().transpose
```

### Remove all missing values from dataframe

```python
removeAllDF= df.na.drop()
```

### Replace missing values with the column mean

```python
from pyspark.sql.functions import avg
imputeDF = df

for x in imputeDF.columns:
    meanValue = removeAllDF.agg(avg(x)).first()[0]
    print(x, meanValue)
    imputeDF = imputeDF.na.fill(meanValue, [x])
```

# pyspark connect to SQL postgresql

Correct configuration of postgresql or other sql jar in the env virtual 

https://rajansahu713.medium.com/connecting-apache-spark-to-different-relational-databases-locally-and-aws-using-pyspark-python-c2d77732081b

https://www.machinelearningplus.com/pyspark/pyspark-connect-to-postgresql/?expand_article=1
