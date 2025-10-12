# Testing schema changes/evolution

spark.sql("ALTER TABLE local.db.employee ADD COLUMN bonus DOUBLE")

spark.sql("UPDATE local.db.employee SET bonus = 5000 WHERE performance_score > 4.0")

spark.sql("INSERT INTO local.db.employee VALUES (7, 'Grace', 1, 88000, 0.0, 4.3, current_timestamp(), 3000)")

spark.sql("""
INSERT INTO local.db.department VALUES
(4, 'Services', current_timestamp())
""")

