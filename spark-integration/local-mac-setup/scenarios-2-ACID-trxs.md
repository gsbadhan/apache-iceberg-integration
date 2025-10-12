# Testing ACID transactions on iceberg tables


`spark.sql("UPDATE local.db.employee SET salary = salary + 10000 WHERE performance_score >= 4.5")`

`spark.sql("INSERT INTO local.db.employee VALUES (6, 'Frank', 2, 82000, 90000.0, 4.0, current_timestamp())")`

`spark.sql("DELETE FROM local.db.employee WHERE performance_score < 3.6")`