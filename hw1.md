姓名：竺雷  学号：17061636

## 作业1：尝试执行命令CREATE/DROP/ALTER TABLE/NOT NULL/PRIMA KEY/UNIQUE/SHOW TABLES/DESCRIBE TABLE
```sql
mysql> create table hw1(id int);
Query OK, 0 rows affected (0.04 sec)
##建立一张名为‘hw1’的表格，当中还有一列名叫id的数据，类型为int

mysql> show tables;
+----------------+
| Tables_in_test |
+----------------+
| biaoge1        |
| biaoge2        |
| hw1            |
+----------------+
3 rows in set (0.00 sec)
##使用show tables 显示当前数据库中所有是表格

mysql> alter table hw1
    -> add name varchar(20);
Query OK, 0 rows affected (0.07 sec)
Records: 0  Duplicates: 0  Warnings: 0
##使用alter命令添加一列名叫name，类型为20位字符的数据

mysql> create table hw1(id int NOT NULL,name varchar(20),UNIQUE (id));
Query OK, 0 rows affected (0.04 sec)
##使用NOT NULL约束强制列不接受 NULL 值，UNIQUE 约束唯一标识数据库表中的每条记录,PRIMA KEY 同理 但每个表只能有一个PRIMA KEY 约束

mysql> DESCRIBE hw1;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| id    | int(11)     | YES  |     | NULL    |       |
| name  | varchar(20) | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
2 rows in set (0.00 sec)
##使用DESCRIBE命令显示表格数据类型

mysql> drop table hw1;
Query OK, 0 rows affected (0.01 sec)
##使用drop命令删除表格
```
