### SQL注入

sql存在漏洞，

### PreparedStatement 对象

PreparedStatement可以防止SQL注入。效率更高

新增

删除

更新

查询



### 数据库连接池

数据库连接 - 执行完毕 - 释放

连接 - 释放 十分浪费系统资源

**池化技术：准备一些预先的资源，过来就连接预先准备好的**

编写连接池，实现一个接口 DataSource

> 开源数据源实现

DBCP

C3P0

Druid：阿里巴巴

使用了这些数据库连接池之后，我们在项目开发中就不需要编写连接数据库的代码了

> DBCP

需要用到jar包

commons-dbcp-1.4、commons-pool-1.6







