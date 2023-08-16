#pyspark with jupter installtion 

```
python -m venv spark
```

```
source spark/bin/activate
```

```

pip install --upgrade pip 

```

```

pip install notebook
```


```
pip install pyspark
```


```
pip install findspark

```

#pyspark define inside notebook 


```
import findspark
findspark.init()
import pyspark

from pyspark import SparkContext

sc = SparkContext.getOrCreate()

sqlContext = SQLContext(sc)
```


# pyspark read data from csv file

```
df = sqlContext.read.load('file://<?path_to_file_.csv>',
format='com.databricks.spark.csv', header='true', inferSchema='true' )
```` 

```
df.columns
```


#pyspark connect to SQL postgresql

Correct configuration of postgresql or other sql jar in the env virtual 

https://rajansahu713.medium.com/connecting-apache-spark-to-different-relational-databases-locally-and-aws-using-pyspark-python-c2d77732081b

https://www.machinelearningplus.com/pyspark/pyspark-connect-to-postgresql/?expand_article=1
