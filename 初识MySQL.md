### 初识MySQL

数据库是几乎软件体系中最核心的一个存在

#### 什么是数据库

数据库（**DataBase**，简称**DB**）

概念：长期存放在计算机内，有组织，可共享的大量数据的集合，是一个**数据“仓库”**

作用：保存，并能安全管理数据（如：增删改查等）减少冗余

数据库总览

* 关系型数据库（SQL）
  * MySQL,Oracle , SQL Server , SQLite , DB2 , ...
  * 关系型数据库通过外键关联来建立表与表之间的关系
* 非关系型数据库 ( NOSQL )
  * Redis , MongoDB , ...
  * 非关系型数据库通常指数据以对象的形式存储在数据库中，而对象之间的关系通过每个对象自身的属性来决定

#### 什么是DBMS

数据库管理系统 ( **D**ata**B**ase **M**anagement **S**ystem )

数据库管理软件 , 科学组织和存储数据 , 高效地获取和维护数据

#### MySQL简介

**概念 :** 是现在**流行**的**开源**的,**免费**的 **关系型**数据库

**历史 :** 由瑞典MySQL AB 公司开发，目前属于 Oracle 旗下产品。

**特点：**

* 免费 , 开源数据库
* 小巧 , 功能齐全
* 使用便捷
* 可运行于Windows或Linux操作系统
* 可适用于中小型甚至大型网站应用

#### 安装MySQL

> 建议安装压缩版，安装快，卸载简单

软件下载

[社区版下载](https://dev.mysql.com/downloads/mysql/)

#### 安装步骤

下载后得到 zip 压缩包

解压到自己想要安装到的目录下，请记住该路径

添加环境变量：我的电脑->属性->高级->环境变量

```
选择PATH,在其后面添加: 你的mysql 安装文件下面的bin文件夹
```

新建编辑 my.ini 文件 ,++注意替换成自己的路径位置++

```ini
[mysqld]
basedir=D:\Program Files\mysql-5.7\
datadir=D:\Program Files\mysql-5.7\data\
port=3306
skip-grant-tables 
#最后一行是跳过密码进行登陆 
```

启动管理员模式下的CMD，并将路径切换至mysql下的bin目录，然后输入`mysqld –install` (安装mysql)

----

##### 安装遇到的问题

* 这时就会有童鞋出现问题

由于是最新版的的MySQL，所以需要一个比较新的微软运行库

[下载并安装](https://pan.baidu.com/s/1PVLTL_-AugIWc0xMqVDk3Q)    提取码：0ovs

> 如果链接失效，可自行查找**微软常用运行库合集**

-----

再输入  `mysqld --initialize-insecure --user=mysql` 初始化数据文件

**这时自己的MySQL文件夹下会出现一个data文件夹，证明已经成功**

然后再次启动mysql `net start mysql`

#### DOS命令下连接数据库

打开MySQL命令窗口

- 在DOS命令行窗口进入 **安装目录\mysql\bin**
- 可设置环境变量，设置了环境变量，可以在任意目录打开！

**连接数据库语句 :** mysql -h 服务器主机地址 -u 用户名 -p 用户密码

注意 : -p后面不能加空格,否则会被当做密码的内容,导致登录失败 !

**几个基本的数据库操作命令 :**

```sql
update user set password=password('123456')where user='root'; --修改密码
flush privileges; 		--刷新权限
show databases; 		--查看所有数据库
use dbname；				--打开某个数据库
show tables; 			--显示数据库mysql中所有的表
describe user; 			--显示表mysql数据库中user表的列信息
create database name; 	--创建数据库
use databasename; 		--选择数据库
exit; 					--退出Mysql连接
? 						--命令关键词 
: 						--寻求帮助
--						-- 表示注释
						--所有的语句都使用;结尾
```

