# Testing time tarvel using snapshot_id


# Changes history of employee
`spark.sql("SELECT * FROM local.db.employee.snapshots ORDER BY committed_at DESC").show(false)`

# Travel back to see old employee data
`spark.sql("""
SELECT * FROM local.db.employee 
FOR SYSTEM_TIME AS OF 7115730409057541182
""").show()`


# Changes history of department
`spark.sql("SELECT * FROM local.db.department.snapshots ORDER BY committed_at DESC").show(false)`

# Travel back to see old department data
`spark.sql("""
SELECT * FROM local.db.department 
FOR SYSTEM_TIME AS OF 5965242925823455439
""").show()`