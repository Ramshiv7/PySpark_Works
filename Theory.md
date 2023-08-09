### SparkSession : 
- Entry point to the Spark 

### SparkContext :
- Entry Point to the PySpark Functionality to the RDD, and Cluster


### Benefits of RDD in Pyspark : 

#### In-Memory Computation : 
- Pyspark allows to store data in-memory & cache RDD vs Map Reduce ( IO intensive )
#### Fault Tolerant : 
- Any Failure, it auto loads data from other partitions
#### Lazy Computation : 
- Pyspark evaluates the transformation only if the actions gets called 
#### Partitions : 
- By Defaults, When RDD is created from Data, the elements are partitioned

#### Inbuild Optimization 
#### Cache & Persistance 
#### Immutable 
#### Ansi SQL Support 


# RDD operations :

### RDD Transformations : 

- it is Lazy Operations, instead of updating the RDD, a new RDD is returned
#### flatMap()
- flattens the RDD after applying the function and returns a new RDD.
####  map() 
- transformation is used the apply any complex operations like adding a column, updating a column e.t.c, 
#### collect()
- collect all elements from distributed nodes
#### reduceByKey() 
- reduceByKey() merges the values for each key with the function specified. 
#### sortByKey() 
-  transformation is used to sort RDD elements on key. In our example, first, we convert RDD[(String,Int]) to RDD[(Int, String]) using map transformation and apply sortByKey which ideally does sort on an integer value.
#### filter() 
- Transformation is used to filter the records in an RDD.

### RDD Actions : 

- operations that triggers computation and returns RDD Values
#### count() 
- Returns the number of records in an RDD 
#### max() 
- Returns max record.
#### reduce() 
- Reduces the records to single, we can use this to count or sum. 
#### take() 
-  Returns the record specified as an argument.
#### collect() 
- Returns all data from RDD as an array. Be careful when you use this action when you are working with huge RDD with millions and billions of data as you may run out of memory on the driver.
#### saveAsTextFile() 
- Using saveAsTextFile action, we can write the RDD to a text file

# Types of RDD

#### Shuffle Operations RDD

- Mechanism to Re-Distribute the data Across different executors.
- It triggers during GroupByKey(), reduceByKey(), join() on RDDs 
- Operations that Triggers -> repartition(), coalesce(), groupByKey(), reduceByKey(), cogroup(), join() but NOT countByKey()

### RDD Cache 

- By Default Saves RDD computations to Memory_Only Storage Level, in JVM Heap Unserialized 
- cache() internally calls persist() to cache the result set of RDD

### RDD Persist 

- Stores RDD to one of the Storage_Levels - Memory Only, Memory & Disk etc
- Can also - unpersist()

## Shared Variables 

#### Broadcast Variables ( Read-only Shared Variables )
- read-only shared variables that are cached and avaiable in all nodes in a cluster in-order to access or use by task. ex : zip code, pin etc
- look-up data

#### Accumlator Variables ( Updatable Shared Variables )

- shared variable that are only "added" through associative and commulative operation 
- named accumlators - visible in pyspark UI, Recommended 
- unnamed accumlators - Non visible in UI 


# Data Frame 

- rdd.toDF()

- rdd.toDF('col1', 'col2')

- spark.createDataFrame(rdd).toDF('col1', 'col2')

- df.rdd

Supports Spark, Yarn, Mesos Cluster Managers
Distributed Processing ( Parallelize )

Spark vs pyspark 

Lineage 
Transformation vs 
static typed language 


UDF is last resort 

Spark Concepts 

Scala based spark has more functionalities 

group by 
order by 
join 
aggregate by 
General Functions 

Spark 

ML concept 