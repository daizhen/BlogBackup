---
title: Hive commands
date: 2016-11-18 16:56:02
tags:Big data, Hadoop, Hive 
---
创建外部表, 使用external关键字。 外部表的好处是在执行drop table之后，数据文件不会删除。 此语句只是做一个表结构到已有的数据文件的映射。location处指定的是hdfs中的文件名。
```
Create external table XXX(Field1 int, Field2 string) 
ROW FORMAT DELIMITED
FIELDS TERMINATED BY '|'
STORED AS TEXTFILE
location '/data/XXXX.txt';
```
如果指定的location是一个文件夹而不是特定文件的话，则把文件夹下所有的数据文件映射到表结构中去。
```
Create external table XXX(Field1 int, Field2 string) 
ROW FORMAT DELIMITED
FIELDS TERMINATED BY '|'
STORED AS TEXTFILE
location '/data/';
```
