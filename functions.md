RDD : 

spark.sparkContext.parallelize(rdd_data, num_of_paritions)

spark.sparkContext.textFile('file_name')

rdd = spark.sparkContext.wholeTextFiles('file_name')

rdd.getNumPartitions()

new_rdd = rdd.repartition(4)

RDD Transformations :

rdd2 = rdd.flatMap(lambda x: x.split(" ")) -- returns a new rdd

rdd.map()

rdd.reduceByKey(lambda a,b: a+b)

rdd.sortByKey()

rdd.collect()

rdd.filter(lambda x: 'an' in x[1])

