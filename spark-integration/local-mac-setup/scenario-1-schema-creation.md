# Create tables using iceberg

# department
spark.sql("""
CREATE TABLE local.db.department (
    department_id INT,
    name STRING,
    last_updated TIMESTAMP
) USING iceberg
PARTITIONED BY (department_id)
""")

spark.sql("""
INSERT INTO local.db.department VALUES
(1, 'Engineering', current_timestamp()),
(2, 'Sales', current_timestamp()),
(3, 'Marketing', current_timestamp())
""")

spark.sql("select * from local.db.department").show()


# employee
spark.sql("""
CREATE TABLE local.db.employee (
    employee_id INT,
    name STRING,
    department_id INT,
    salary DOUBLE,
    sales_amount DOUBLE,
    performance_score DOUBLE,
    last_updated TIMESTAMP
) USING iceberg
PARTITIONED BY (employee_id)
""")

spark.sql("""
INSERT INTO local.db.employee VALUES
(1, 'Alice', 2, 80000, 150000.0, 4.2, current_timestamp()),
(2, 'Bob', 2, 90000, 0.0, 4.5, current_timestamp()),
(3, 'Charlie', 2, 75000, 120000.0, 3.8, current_timestamp()),
(4, 'Diana', 1, 95000, 0.0, 4.7, current_timestamp()),
(5, 'Eve', 3, 70000, 80000.0, 3.5, current_timestamp())
""")

spark.sql("select * from local.db.employee").show()

