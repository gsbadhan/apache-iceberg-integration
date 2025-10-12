# Testing complex queries

`spark.sql("""
select e.*, d.* from local.db.employee e join local.db.department d 
on e.department_id = d.department_id
""").show()`