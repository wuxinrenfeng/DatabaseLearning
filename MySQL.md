### MySQL

JavaEE：企业级Java开发  web

前端（页面：展示，数据）

后台（连接点：连接数据库 JDBC，连接前端（控制，控制视图跳转，和给前端传递数据））

数据库（存数据，Txt，Excel，word）

> 只会写代码，学好数据库，基本混饭吃；
>
> 操作系统，数据结构与算法！当一个不错的程序员
>
> 离散数学，数字电路，体系结构，编译原理 + 实战经验，高级程序员-优秀程序员

#### 为什么要学数据库

岗位需求

现在的世界，大数据时代~，得数据者得天下

被迫需求：存数据 去IOE

数据库是所有软件体系中最核心得存在 DBA

#### 什么是数据库

数据库（DB，DataBase）

概念：数据仓库，软件，安装在操作系统（window，linux，mac）之上 SQL，可以存储大量得数据，500w

作用：存取数据，管理数据 Excel

#### 数据库分类

**关系型数据库**：（SQL）

* MySQL,Oracle,Sql Server,DB2,SQLlite
* 通过表和表之间，行和列之间的关系进行数据的存储，学员信息表，考勤表

**非关系型数据库**：（NoSQL）Not Only

* Redis，MongDB
* 非关系型数据库，对象存储，通过对象的自身的属性来决定

#### DBMS（数据库管理系统）

* 数据库的管理软件，科学有效的管理我们的数据。维护和获取数据；
* MySQL，数据库管理系统(管理和操作数据)

#### MySQL简介

MySQL是一个关系型数据库管理系统

前世：瑞典MySQL AB公司

今身：属于 Oracle 旗下产品

MySQL是最好的 RDBMS（Relational DataBase Management System，关系型数据库管理系统）应用软件之一

开源的数据库软件~

体积小，速度快，总体拥有成本低，招人成本比较低，所有人必须会~

中小型网站、或者大型网站，集群

官网：https://www.mysql.com/

5.7 稳定版

8.0 

安装建议：

尽量不要使用 exe，注册表

尽可能使用压缩包安装~

#### 安装MySQL

解压

把包放到自己电脑的环境文件夹

配置环境变量

新建mysql配置文件

```ini
[mysqld]
#目录一定要换成自己的
basedir=D:\Program Files (x86)\MySQL\mysql-8.0.21\
datadir=D:\Program Files (x86)\MySQL\mysql-8.0.21\data\
port=3306
skip-grant-tables
```

启动管理员模式下的CMD，运行所有的服务

安装mysql服务

初始化数据库文件

启动mysql，初始化密码

进入mysql通过命令行（-p 后面不要加空格），修改密码（sql语句后面一定不要忘了加分号）

注释掉ini中的跳过密码

重启mysql，连接测试，如果连接成功就ok

> sc delete mysql  清空服务







