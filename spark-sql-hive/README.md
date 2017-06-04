# Spark-SQL-Hive
​    Spark-SQL on Hive对于企业来讲是一个不可或缺的部分。在Spark出现之前，MapReduce生态系统中，一直是由Hive担任着SQL查询分析的重任。从软件维护角度来看，对于遗留应用的迁移，不管是语法层面的兼容还是元数据管理层面复用，Hive的影子仍将在很长时间内存在。

​    在Spark 2.0版本之前，用户如果要在Spark SQL中使用Hive的一些功能，需要构造与SparkContext相对应的HiveContext来作为入口。从Spark 2.0版本开始，由于引入了ANTLR，架构层次上更加清晰。对于用户来讲，也不再需要构造HiveContext，而是通过SparkSession的enableHiveSupport操作来走Hive的路线。

```scala
val spark = SparkSession.builder().enableHiveSupport().getOrCreate()
```

- ## 概述

​    类似于Spark SQL中的SessionState类，HiveSessionState起到了主要作用，如图所示：





