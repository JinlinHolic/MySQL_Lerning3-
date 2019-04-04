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





