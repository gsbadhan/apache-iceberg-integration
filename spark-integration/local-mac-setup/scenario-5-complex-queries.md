# Testing complex queries

`spark.sql("""
select e.*, d.* from local.db.employee e join local.db.department d 
on e.department_id = d.department_id
""").show()`


`spark.sql("select department_id,count(employee_id),max(salary),avg(salary), min(salary), sum(bonus) from local.db.employee group by department_id").show()`