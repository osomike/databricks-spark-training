# Exercise 01: Exploring Narrow Transformations with PySpark
In this exercise, you will work with a dataset to explore and understand narrow transformations in PySpark. Narrow transformations are operations where each input partition contributes to only one output partition. Examples include `select`, `filter`, and `withColumn`.

You will be using the New York Taxi dataset, which contains detailed information about taxi trips in New York City. This dataset provides comprehensive details about each taxi trip, including temporal and spatial information, passenger count, fare details, and payment information.

To get more familiar with, it here a description of its content:

- **vendor_id** (*StringType*): A code indicating the provider that collected the record.
- **pickup_datetime** (*TimestampType*): The date and time when the meter was engaged.
- **dropoff_datetime** (*TimestampType*): The date and time when the meter was disengaged.
- **passenger_count** (*IntegerType*): The number of passengers in the vehicle, as reported by the driver.
- **trip_distance** (*DoubleType*): The distance of the trip in miles, as reported by the taximeter.
- **pickup_longitude** (*DoubleType*): Longitude where the trip started.
- **pickup_latitude** (*DoubleType*): Latitude where the trip started.
- **rate_code_id** (*IntegerType*): The final rate code in effect at the end of the trip.
- **store_and_fwd_flag** (*StringType*): Indicates whether the trip record was stored in the vehicle's memory before sending to the vendor (e.g., due to lack of a connection).
- **dropoff_longitude** (*DoubleType*): Longitude where the trip ended.
- **dropoff_latitude** (*DoubleType*): Latitude where the trip ended.
- **payment_type** (*StringType*): A code signifying how the passenger paid for the trip.
- **fare_amount** (*DoubleType*): The time-and-distance fare calculated by the meter.
- **extra** (*DoubleType*): Miscellaneous extras and surcharges, such as rush hour and overnight charges.
- **mta_tax** (*DoubleType*): A tax automatically triggered based on the metered rate in use.
- **tip_amount** (*DoubleType*): Tip amount; this field is automatically populated for credit card tips.
- **tolls_amount** (*DoubleType*): Total amount of all tolls paid during the trip.
- **total_amount** (*DoubleType*): The total amount charged to passengers, not including cash tips.

The goal of this excersise is to perform various transformations on it and observe their effects. 

You will:
- Create a new column `surcharge_amount` containing a surcharge amount where the surcharge is 10% of the fare amount `fare_amount`.
- Check if the trip is a long trip or not by adding a column `is_long_trip`, considering that a long trip is defined as having a trip distance greater than 10 miles.
- Add a column `trip_category` based on the number of passengers in the car, categorizing them into 'small group', 'medium group', and 'big group'. The group sizes are defined as follows:
    - `small group`: 1-2 passengers
    - `medium group`: 3-4 passengers
    - `big group`: 5 or more passengers
- Select trips made by VTS only and then select a subset of columns including `vendor_id`, `total_amount`, `surcharge_amount`, `trip_distance`, `is_long_trip`, `passenger_count`, and `trip_category`.

## Objectives

1. **Load the Dataset**: The full New York Taxi dataset is already available in the workspace at the location `/databricks-datasets/nyctaxi/tables/nyctaxi_yellow`, however for initial tests you will use a sampled version of it available at `/mnt/dls/data/big/nyctaxi_yellow_partitioned_sampled`.
2. **Apply Transformations**: Perform narrow transformations such as `select`, `filter`, and `withColumn` on the dataset.
3. **Analyze Query Plans**: Use the `explain` method to understand the logical and physical plans generated by Spark for these transformations.
4. **Measure Performance**: Compare the performance of operations on partitioned and non-partitioned data. You will find the following partitioned datasets:
    - Full dataset (1.6 billion records) at `/mnt/dls/data/big/nyctaxi_yellow_partitioned`.
    - Sampled dataset (1.6 million records) at `/mnt/dls/data/big/nyctaxi_yellow_partitioned_sampled`.

## Instructions

1. **Setup the Environment**: 
    - Login into the Databricks workspace, create a notebook and attach it to your corresponding cluster number (`cls-01`, `cls-02`, etc)
2. **Load Data**: Load the New York Taxi dataset from the specified locations.
3. **Transform Data**: Apply transformations to create new columns like `surcharge_amount`, `is_long_trip`, and `trip_category`, and filter the dataset to include only VTS trips.
4. **Query Plans**: Use the `explain` method to analyze the query plans for your transformations.
5. **Performance Measurement**: Measure the time taken for operations on both partitioned and non-partitioned data and compare the results. You can store your results at the location `/mnt/dls/outputs/<your_name>` to avoid people writting results at the same location.

By the end of this exercise, you should have a deeper understanding of narrow transformations in PySpark and how to analyze and optimize your Spark jobs.
