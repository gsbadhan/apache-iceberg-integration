

# Download and setup apache spark 3.5
1. create folder `mkdir iceberg_spark` and go inside
2. `wget https://archive.apache.org/dist/spark/spark-3.5.3/spark-3.5.3-bin-hadoop3.tgz`
3. `tar -xzf spark-3.5.3-bin-hadoop3.tgz`
3. `sudo mv spark-3.5.3-bin-hadoop3 /opt/spark-3.5.3`
4. `sudo ln -sf /opt/spark-3.5.3 /opt/spark`
5. `echo 'export PATH="/opt/spark/bin:$PATH"' >> ~/.bash_profile`
6. `source ~/.bash_profile`
7. `/opt/spark-3.5.3/bin/spark-shell --version`

# Download and setup iceberg-spark-runtime
1. `wget https://repo1.maven.org/maven2/org/apache/iceberg/iceberg-spark-runtime-3.5_2.12/1.4.2/iceberg-spark-runtime-3.5_2.12-1.4.2.jar`

# Create local storage folder to store data
1. create folder `mkdir warehouse` inside `iceberg_spark` 

# Start apache spark
1. `spark-shell --packages org.apache.iceberg:iceberg-spark-runtime-3.5_2.12:1.4.2 \
--conf spark.sql.extensions=org.apache.iceberg.spark.extensions.IcebergSparkSessionExtensions \
--conf spark.sql.catalog.local=org.apache.iceberg.spark.SparkCatalog \
--conf spark.sql.catalog.local.type=hadoop \
--conf spark.sql.catalog.local.warehouse=~/iceberg_spark/warehouse`
2. you will see scala termonal :)
