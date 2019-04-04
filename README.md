# MySQL_Lerning3-

##  2.1 MySQL 基础 （二）- 表操作

### 1. MySQL表数据类型

MySQL中定义数据字段的类型对你数据库的优化是非常重要的。MySQL支持多种类型，大致可以分为三类：数值、日期/时间和字符串(字符)类型。

#### 数值类型

MySQL支持所有标准SQL数值数据类型。

这些类型包括严格数值数据类型(INTEGER、SMALLINT、DECIMAL和NUMERIC)，以及近似数值数据类型(FLOAT、REAL和DOUBLE PRECISION)。

关键字INT是INTEGER的同义词，关键字DEC是DECIMAL的同义词。

BIT数据类型保存位字段值，并且支持MyISAM、MEMORY、InnoDB和BDB表。

作为SQL标准的扩展，MySQL也支持整数类型TINYINT、MEDIUMINT和BIGINT。下面的表显示了需要的每个整数类型的存储和范围。
![WeChat Image_20190403212138](https://user-images.githubusercontent.com/43989688/55506761-8b8d9a00-5656-11e9-9538-b8e34a965270.png)

### 日期和时间类型

表示时间值的日期和时间类型为DATETIME、DATE、TIMESTAMP、TIME和YEAR。

每个时间类型有一个有效值范围和一个"零"值，当指定不合法的MySQL不能表示的值时使用"零"值。

### 字符串类型

字符串类型指CHAR、VARCHAR、BINARY、VARBINARY、BLOB、TEXT、ENUM和SET。该节描述了这些类型如何工作以及如何在查询中使用这些类型。

参考链接:http://www.runoob.com/mysql/mysql-data-types.html

### 2. 用SQL语句创建表

语句解释 设定列类型 、大小、约束 设定主键。

语法:   USE 数据库名(database) CREATE TABLE 表名(列名 类型(大小) pk,
         
                                               (列名 类型(大小),
                                               
                                               (列名 类型(大小)
                                               
                                                ......);

DROP TABLE 表的名称 --删除整张表

CREATE TABLE 表的名称 --建立表和列

举例:建立表和列 并设定id为主键(PK)

![WeChat Image_20190404171541](https://user-images.githubusercontent.com/43989688/55567181-70299a00-56fd-11e9-894e-050d809a37d4.png)

###  用SQL语句向表中添加数据

SQL语言使用insert语句向数据库表格中插入或添加新的数据行。

insert into tablename 

(first_column,...last_column) 

values (first_value,...last_value);  上图有举例
注意: 存储在列中的数据在values子句中给出，必须每列一个值,如果当前values没有值 就输入NULL。

指定列名插入: INSERT INTO `DATABASE`.`TABLE` (COLUMN) VALUES ('CONTENT')
不指定列名插入:INSERT INTO table VALUES('CONTENT','CONTENT','CONTENT'...);

### 用SQL语句删除表(drop、truncate和delete的用法)

SQL中的语法

   1、drop table 表名称                         eg: drop table  dbo.Sys_Test
   
   2、truncate table 表名称                     eg: truncate  table dbo.Sys_Test
   
   3、delete from 表名称 where 列名称 = 值      eg: delete from dbo.Sys_Test where test='test'
 
drop，truncate，delete区别

  1、drop (删除表)：删除内容和定义，释放空间。简单来说就是把整个表去掉.以后要新增数据是不可能的,除非新增一个表。

       drop语句将删除表的结构被依赖的约束（constrain),触发器（trigger)索引（index);依赖于该表的存储过程/函数将被保留，但其状态会变为：invalid。

    2、truncate (清空表中的数据)：删除内容、释放空间但不删除定义(保留表的数据结构)。与drop不同的是,只是清空表数据而已。

       注意:truncate 不能删除行数据,要删就要把表清空。

    3、delete (删除表中的数据)：delete 语句用于删除表中的行。delete语句执行删除的过程是每次从表中删除一行，并且同时将该行的删除操作作为事务记录在日志中保存

       以便进行进行回滚操作。

       truncate与不带where的delete ：只删除数据，而不删除表的结构（定义）

    4、truncate table 删除表中的所有行，但表结构及其列、约束、索引等保持不变。新行标识所用的计数值重置为该列的种子。如果想保留标识计数值，请改用delete。

       如果要删除表定义及其数据，请使用 drop table 语句。 
       
    5、对于由foreign key约束引用的表，不能使用truncate table ，而应使用不带where子句的delete语句。由于truncate table 记录在日志中，所以它不能激活触发器。

    6、执行速度，一般来说: drop> truncate > delete。

    7、delete语句是数据库操作语言(dml)，这个操作会放到 rollback segement 中，事务提交之后才生效；如果有相应的 trigger，执行的时候将被触发。

             truncate、drop 是数据库定义语言(ddl)，操作立即生效，原数据不放到 rollback segment 中，不能回滚，操作不触发 trigger。 
             
 参考链接:https://www.cnblogs.com/1312mn/p/4422396.html
 
 
### 用SQL语句修改表

#### 修改列名

ALTER TABLE 表名 CHANGE 列名 新列名 列类型


## 作业

### 项目三：超过5名学生的课（难度：简单）

创建如下所示的courses 表 ，有: student (学生) 和 class (课程)。

+---------+------------+

| student | class      |

+---------+------------+‘’

| A       | Math       |

| B      | English    |

| C       | Math       |

| D       | Biology    |

| E       | Math       |

| F       | Computer   |

| G       | Math       |

| H       | Math       |

| I       | Math       |

| A      | Math       |

+---------+------------+

编写一个 SQL 查询，列出所有超过或等于5名学生的课。应该输出:

+---------+

| class   |

+---------+

| Math    |

+---------+

Note:学生在每个课中不应被重复计算。

![WeChat Image_20190404190434](https://user-images.githubusercontent.com/43989688/55574386-90148a00-570c-11e9-8176-fca920964e46.png)




