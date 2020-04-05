姓名：竺雷  学号：17061636

## 作业4：运行下列存储过程和函数
mysql> DELIMITER $$
mysql> CREATE PROCEDURE proce_employee_sal1 ()
    -> BEGIN
    -> SELECT sal
    -> FROM t_employee2;
    -> END$$

##使用定义的函数调出命令
mysql> DELIMITER;
    -> CALL proce_employee_sal1();
+------+
| sal  |
+------+
|  800 |
| 1600 |
| 1250 |
| 2975 |
| 1250 |
| 2450 |
| 3000 |
| 5000 |
| 1500 |
| 1100 |
|  950 |
| 3000 |
| 1300 |
+------+
13 rows in set (0.01 sec)

##同理，使用另一命令函数
mysql> DELIMITER $$
mysql> CREATE FUNCTION func_employee_sal (empno INT)
    -> RETURNS DOUBLE
    -> BEGIN
    -> RETURN (SELECT sal FROM t_employee2 WHERE t_employee2.empno = empno);
    -> END$$

mysql> DELIMITER;
    -> SELECT func_employee_sal(7369);
+-------------------------+
| func_employee_sal(7369) |
+-------------------------+
|                     800 |
+-------------------------+
1 row in set (0.01 sec)
##可以得到对应的数据
