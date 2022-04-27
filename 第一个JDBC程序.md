### JDBC（重点）

#### 数据库驱动

驱动：声卡、显卡、数据库

我们的程序会通过**数据库驱动**，和数据库打交道

#### JDBC

SUN公司为了简化开发人员的（对数据库的统一）操作，提供了一个（Java操作数据库的）规范 ，俗称 **JDBC**

这些规范的实现由具体的厂商去做

对于开发人员来说，我们只需要掌握 JDBC 接口的操作即可

java.sql

javax.sql

还需要导入一个数据库驱动包

#### 第一个JDBC程序

> 创建测试数据库

创建一个普通项目

导入数据库驱动

编写测试代码

```java
public class JdbcFirstDemo {
    public static void main(String[] args) throws ClassNotFoundException, SQLException {
        //加载驱动
        Class.forName("com.mysql.cj.jdbc.Driver");  //固定写法

        //用户信息和URL
        String url = "jdbc:mysql://localhost:3306/jdbcstudy?useUnicode=true&characterEncoding=utf8&useSSL=true";
        String username = "root";
        String password = "123456";
        //连接成功，数据库对象  connection代表数据库
        Connection connection = DriverManager.getConnection(url, username, password);
        //执行SQL的对象
        Statement statement = connection.createStatement();


        //执行SQL的对象 去执行SQL 可能存在结果
        String sql = "SELECT * FROM users";
        ResultSet resultSet = statement.executeQuery(sql); //返回的结果集 结果集中封装了我们全部的查询出来的结果

        while(resultSet.next()){
            System.out.println("id=" + resultSet.getObject("id"));
            System.out.println("name=" + resultSet.getObject("NAME"));
            System.out.println("pwd=" + resultSet.getObject("PASSWORD"));
            System.out.println("email=" + resultSet.getObject("email"));
            System.out.println("birth=" + resultSet.getObject("birthday"));
        }
        //释放连接
        resultSet.close();
        statement.close();
        connection.close();
    }
}
```

步骤总结：

加载驱动

连接数据库 DriveManager

获得执行sql的对象，statement

获得返回的结果集

释放连接

> DriverManager

```java
DriverManager.registerDriver(new com.mysql.cj.jdbc.Driver());
Class.forName("com.mysql.cj.jdbc.Driver");  //固定写法 加载驱动
Connection connection = DriverManager.getConnection(url, username, password);
//connection 代表数据库
//数据库设置自动提交
//事务提交
//事务回滚
connection.commit();
connection.rollback();
connection.setAutoCommit();
```

> URL

```java
String url = "jdbc:mysql://localhost:3306/jdbcstudy?useUnicode=true&characterEncoding=utf8&useSSL=true";
//mysql 默认端口3306
//协议://主机地址：端口号/数据库名？参数1&参数2&参数3
//oracle 默认端口1521
//jdbc:oracle:thin:@localhost:1521:sid
```

> statement 执行SQL的对象   prepareStatement 执行SQL的对象

```java
String sql = "SELECT * FROM users";
statement.executeQuery(); //查询操作 返回结果集
statement.execute(); //执行任何SQL
statement.executeUpdate(); //更新、插入、删除都是用这个，返回一个受影响的行数
```

> ResultSet 查询的结果集：封装了所有的查询结果

获得指定的数据类型

```java
resultSet.getObject(); //在不知道列类型的情况下使用
resultSet.getString(); //如果知道列的类型就使用指定的类型
resultSet.getInt();
resultSet.getFloat();
resultSet.getDate();
```

遍历,指针

```java
resultSet.beforeFirst(); //移动到最前面
resultSet.afterLast(); //移动到最后面
resultSet.next(); //移动到下一个数据
resultSet.previous(); //移动到前一行
resultSet.absolute(row); //移动到指定行
```

> 释放资源

```java
//释放连接
resultSet.close();
statement.close();
connection.close(); //耗资源，必须关掉
```