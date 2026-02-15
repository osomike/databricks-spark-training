# Databricks Spark Training

![Python](https://img.shields.io/badge/Python-3.8+-blue)
![Spark](https://img.shields.io/badge/Apache%20Spark-3.x-orange)
![Databricks](https://img.shields.io/badge/Databricks-Runtime%2013+-red)

Hands-on PySpark training covering performance optimization techniques used in production data engineering pipelines.

## Skills Covered

`PySpark` `Query Optimization` `Data Skew Handling` `Adaptive Query Execution` `Partitioning` `Join Strategies` `Spark UI Analysis`

## Repository Structure

```
databricks-spark-training/
├── notebooks/
│   ├── Pyspark - 01 - Refreshing core concepts
│   ├── Pyspark - 02 - Query plans
│   ├── Pyspark - 03 - Data Skew
├── exercises/
│   ├── ex01/
│   │   └── Ex01_instructions.md
│   ├── ex02/
│   │   └── Ex02_instructions.md
```

## Course Content

### Notebooks

1. **Pyspark - 01 - Refreshing core concepts**
   - Spark's architectural foundation
   - Spark's unified framework
   - Working with RDDs (Resilient Distributed Datasets)
   - Lazy vs eager evaluation in Spark
   
2. **Pyspark - 02 - Query plans**
   - Understanding Spark execution plans
   - Examples of narrow transformations (select, filter, withColumn)
   - Examples of wide transformations (repartition, coalesce, join, groupBy)
   - Analyzing query performance with explain()

3. **Pyspark - 03 - Data Skew**
   - Identifying data skew problems
   - Handling skewed data with salting techniques
   - Working with Adaptive Query Execution (AQE)
   - Performance comparison between different approaches

### Exercises

1. **Exercise 01: Exploring Narrow Transformations with PySpark**
   - Work with the New York Taxi dataset
   - Perform various narrow transformations (select, filter, withColumn)
   - Analyze query plans
   - Compare performance between partitioned and non-partitioned data

2. **Exercise 02: Exploring Joins with PySpark**
   - Load and work with the New York Taxi dataset
   - Create and join with smaller datasets
   - Analyze join query plans
   - Measure join performance and explore optimization strategies

## Getting Started

1. **Set up your Databricks environment**:
   - Log in to your Databricks workspace
   - You can set up your GitHub account on the workspace so you can clone this repository right away (this is not mandatory)
   - Listen to instructions about which cluster you should use

## Prerequisites

- Basic understanding of Python and distributed computing
- Access to a Databricks workspace

## Resources

- [Apache Spark Documentation](https://spark.apache.org/docs/latest/)
- [Databricks Documentation](https://docs.databricks.com/)
- [PySpark API Reference](https://spark.apache.org/docs/latest/api/python/)

---

Happy Learning!
