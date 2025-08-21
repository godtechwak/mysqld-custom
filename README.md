# Description
DBA가 자주 사용하는 mysql 명령어를 타이핑 없이 단축키로 수행할 수 있는 실행파일입니다.

# How to Use
`tc{number}`             : SHOW CREATE TABLE table

`tc {table name}`        : SHOW CREATE TABLE table

`ts{number}`             : SHOW STATUS TABLE LIKE 'table'

`ts {table name}`        : SHOW STATUS TABLE LIKE 'table'

`tt`                     : TABLE LIST

`dc`                     : CREATE DATABASE database

`dds`                    : Database Size

`dds{number}`            : Database Size Detail

`dd{number}`             : Choose Database

`ps`                     : SHOW PROCESSLIST

`psf`                    : SHOW FULL PROCESSLIST

`uu`                     : SHOW USERS

`uuc{number}`            : SHOW CREATE USER

`uug{number}`            : SHOW GRANTS FOR USER

`sv`                     : SESSION VARIABLES

`gv`                     : GLOBAL VARIABLES

`gs`                     : GLOBAL STATUS

`ss`                     : SESSION STATUS

`qq{number} {table name}`: SELECT LIMIT QUERY

`ml`                     : metadata lock

`dl`                     : data lock

`aurora`                 : OPEN AURORA PAGE

`aurorakill`             : KILL QUERY FOR AURORA

`kill`                   : KILL QUERY FOR MYSQL

# Examples
```sql
mysql> \\dds
+--------+--------------+-----------------+-------------------+
| number | table_schema | index_data_size | Percentage(%)     |
+--------+--------------+-----------------+-------------------+
|      1 | sys          | 16.00 KiB       | __________(0.2%)  |
|      2 | test         | 16.00 KiB       | __________(0.2%)  |
|      3 | mysql        | 7.88 MiB        | ++++++++++(99.6%) |
+--------+--------------+-----------------+-------------------+
3 rows in set (0.02 sec)

mysql> \\dds2
+------------+--------------+-----------------+--------------------+------------+
| table_name | table_schema | index_data_size | Percentage(%)      | table_rows |
+------------+--------------+-----------------+--------------------+------------+
| employee   | test         | 16.00 KiB       | ++++++++++(100.0%) | 1          |
+------------+--------------+-----------------+--------------------+------------+

mysql> \\tt
+--------+------------+
| number | TABLE_NAME |
+--------+------------+
|      1 | employee   |
+--------+------------+
1 row in set (0.01 sec)

mysql> \\tc1
*************************** 1. row ***************************
       Table: employee
Create Table: CREATE TABLE `employee` (
  `id` int NOT NULL,
  `name` varchar(100) DEFAULT NULL,
  `created_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci
1 row in set (0.00 sec)
```
