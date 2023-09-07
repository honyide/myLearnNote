# MySQL

## 面试题

什么是事务,以及事务的四大特性?
事务的隔离级别有哪些,MySQL默认是哪个?
内连接与左外连接的区别是什么?
常用的存储引擎?InnoDB与MyISAM的区别?
MySQL默认InnoDB引擎的索引是什么数据结构?
如何查看MySQL的执行计划?
索引失效的情况有哪些?
什么是回表查询?
什么是MVCC?
MySQL主从复制的原理是什么?
主从复制之后的读写分离如何实现?
数据库的分库分表如何实现?



## 基础篇

### MysQL概述

启动与停止命令： net start  +[数据库名] ， net stop  +[数据库名]

客户端连接

<img src="C:\Users\xie\AppData\Roaming\Typora\typora-user-images\image-20230907105527188.png" alt="image-20230907105527188" style="zoom: 67%;" />

<img src="C:\Users\xie\AppData\Roaming\Typora\typora-user-images\image-20230907105547596.png" alt="image-20230907105547596" style="zoom: 67%;" />





SQL

SQL通用语法
SQL语句可以单行或多行书写，以分号结尾。

1.SQL语句可以使用空格/缩进来增强语句的可读性

2.MySQL数据库的SQL语句不区分大小写，关键字建议使用大写
3.注释:
单行注释:-- 注释内容或# 注释内容(MySQL特有)
多行注释:/*注释内容*/

![image-20230907110547714](C:\Users\xie\AppData\Roaming\Typora\typora-user-images\image-20230907110547714.png)

![image-20230907110836115](C:\Users\xie\AppData\Roaming\Typora\typora-user-images\image-20230907110836115.png)

函数
约束

多表查询
事务

## 进阶篇

存储引擎
索引
sQL优化
视图/存储过程/触发器

锁
InnoDB核心
MySQL管理

## 运维篇

日志
主从复制
分库分表
读写分离

















































































