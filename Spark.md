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

# pyspark run a custom fuction stored as .py 

```python
%run -i ./<path?to?the?funtion>.py
```

# pyspark read data from csv file

```python
df = sqlContext.read.load('file://<?path_to_file_.csv>',
format='com.databricks.spark.csv', header='true', inferSchema='true' )
````

# Show csv schema and explore 

### Show the numbers of rows and columns in df

```python
df.count(), len(df.columns)
```

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

# Data Manipulation 

### Remove all missing values from dataframe

```python
df = df.na.drop()
```

### Filter data using filter() command
#### Using a one-tenth of the data subset by calling filter() and using the rowID column
```python
filterDF = df.filter((df.rowID % 10) == 0) 
```
#### Filter data and count how many values are equal to 0.0 

```python
filteredDF.filter(filteredDF.rain_accumulation == 0.0).count()
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

### Assign a list of selected columns to a variable 

```python
featureColumns = ['?çolumn1','?column2',....'?columnN']
```

### Drop specific columns from df
```python
df = df.drop('?çolumn1','?column2',....'?columnN')
```

### Create categorical variable from numerical variable based on specific threshold

```python
binarizer = Binarizer(threshold=<?threshold>, inputCol='column?', outputCol='label')
binarizedDF = binarizer.transform(df) # apply the transformation into binarizedDF 
```
### Aggregated features into a single column: 

```python
assembler = VectorAssembler(inputCols=featureColumns, outputCol='features') # featureColumns is the list of selected columns from before, see assign specific columns to a variable
assembled = assembler.transform(binarizedDF) # apply the transformation into assembled 
```

### Split data into training/test randomSplit()

```python
(trainingData, testData) = assembled.randomSplit([0.8,0.2], seed = 13234) #assembled is the dataframe, 0.8 and 0.2 are the ration between training to test, seed usually is not specified unless needed to be used again. 
```

### Decision Tree 

```python
dt = DecisionTreeClassifier(labelCol='label', featuresCol="features", maxDepth=5, minInstancesPerNode=20, impurity='gini') # The labelCol argument is the column we are trying to predict, featuresCol specifies the aggregated features column, maxDepth is stopping criterion for tree induction based on maximum depth of tree, minInstancesPerNode is stopping criterion for tree induction based on minimum number of samples in a node, and impurity is the impurity measure used to split nodes.

# create a model by training the decision tree. This is done by executing it in a Pipeline
pipeline = Pipeline(stages=[dt]) 
model = pipeline.fit(trainingData)

# make predictions using our test data set
predictions.select("prediction", "label").write.save(path="file:///home/osboxes/Downloads/coursera/big-data-4/predictions.csv", format='com.databricks.spark.csv', header='true') 

# Looking at the first ten rows in the prediction, we can see the prediction matches the input:
predictions.select("prediction", "label").show(10)

# Save predictions to CSV.
predictions.select("prediction", "label").write.save(path="file://<?path>/predictions.csv", format='com.databricks.spark.csv', header='true')

```
### Evaluation of Decision Tree prediction with accurcy calcuation

```python
from pyspark.ml.evaluation import MulticlassClassificationEvaluator # import evaluator
from pyspark.mllib.evaluation import MulticlassMetrics # import metrics for confusion matrix

# Select the output from prediction and label column (see prediction before) from the df and assign it in predictions variable

predictions = predictions.select("prediction", "label")

# Create an instance of MulicalssClassificationEvaluator to determince accuracy of predictions

evaluator = MulticlassClassificationEvaluator(labelCol='label', predictionCol="prediction", metricName="weightedPrecision")  #first two argument specify the names of the label and prediction columns, and the third argument specifies that we want a weighted precision.

accuracy = evaluator.evaluate(predictions)
print("Accuracy = %g " % (accuracy))

```
### Evaluation of Decision Tree prediction with confusion matrix 

```python
from pyspark.mllib.evaluation import MulticlassMetrics # import metrics for confusion matrix

# Display confusion matrix. The MulticlassMetrics class can be used to generate a confusion matrix of our classifier model. However, unlike MulticlassClassificationEvaluator, MulticlassMetrics works with RDDs of numbers and not DataFrames, so we need to convert our predictions DataFrame into an RDD. If we use the rdd attribute of predictions, we see this is an RDD of Rows:

predictions.rdd.take(2)

#Instead, we can map the RDD to tuple to get an RDD of numbers:

predictions.rdd.map(tuple).take(2)

# Create an instance of MulticlassMetrics with this RDD:

metrics = MulticlassMetrics(predictions.rdd.map(tuple))

# The confusionMatrix() function returns a Spark Matrix, which we can convert to a Python Numpy array, and transpose to view:

metrics.confusionMatrix().toArray().transpose()

```


# pyspark connect to SQL postgresql

Correct configuration of postgresql or other sql jar in the env virtual 

https://rajansahu713.medium.com/connecting-apache-spark-to-different-relational-databases-locally-and-aws-using-pyspark-python-c2d77732081b

https://www.machinelearningplus.com/pyspark/pyspark-connect-to-postgresql/?expand_article=1
