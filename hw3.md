姓名：竺雷  学号：17061636

## 作业3：用join改写以下命令
```sql
mysql>select * from t_employee WHERE sal > (
      select sal from t_employee WHERE ename='SMITH');
--该命令意为：选出t_employee表格中sal值大于t_employee表格中ename是SMITH的对应的值的数据，使用jion改写如下
mysql>>select * from t_employee
       inner join t_employee2
       on t_employee.sal > (select sal from t_employee WHERE ename='SMITH')
       order by t_employee.ename;

mysql>select * from t_employee WHERE (sal,job) = (
      select sal,job from t_employee where ename = 'smith');     
--改写如下
mysql>select * from t_employee
      inner join t_employee2
      on t_employee.(sal,job) = (select sal,job from t_employee where ename = 'smith')
      order by t_employee.ename;
