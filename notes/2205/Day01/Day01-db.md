# 数据库技术增强

## 核心要点

* 常见术语
* 数据库及表的设计
* 索引的设计
* 数据库中的事务、锁应用

## 数据库常见术语

* DB (Database):数据库
* DBMS(Database Management System)：数据库管理系统
* SQL(Structured Query Language )：结构化的查询语言

## 数据库的设计

* 数据库名字
* 数据库的字符集
* 数据库中表的数量

**FAQ**

* MySQL中创建数据库的语法是怎样的？

通过 help 'create database' 方式查看创建数据库的语法。

```
CREATE {DATABASE | SCHEMA} [IF NOT EXISTS] db_name
[create_specification] ...

create_specification:
[DEFAULT] CHARACTER SET [=] charset_name
| [DEFAULT] COLLATE [=] collation_name

```

* MySQL如何基于语法创建数据库？

```
CREATE DATABASE IF NOT EXISTS JSDTN2205  CHARACTER SET  utf8mb4;
```
```
CREATE DATABASE IF NOT EXISTS JSDVN2205  COLLATE  utf8mb4_general_ci;
```

* 如何查看Mysql中自带的字符集？

```
show variables like '%collation_%'
```

* 如何删除MySQL中的数据库？

首先通过 help 'drop database' 方式查询删除数据库的语法。

```
DROP {DATABASE | SCHEMA} [IF EXISTS] db_name
```
基于语法实现数据库的删除

```
DROP DATABASE IF EXISTS JSDTN2205;
```

* 如何打开数据库?

```
use JSDTN2205;
```

* 如何查看数据库中有哪些表？

```
show tables;
```

* 如何统计数据库中有多少张表？(mysql5.7)

```
select table_schema,count(*) tables
from information_schema.tables
where table_schema='JSDVN2205'
group by table_schema;
```

