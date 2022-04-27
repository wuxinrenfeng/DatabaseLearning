### statement对象

jdbc中的statement对象用于向数据库发送SQL语句，想完成对数据库的增删改查，只需要通过这个对象向数据库发送增删改查语句即可

Statement 对象的executeUpdate方法，用于向数据库发送增、删、改的 sql 语句，executeUpdate 执行完后，将会返回一个整数（即增删改语句导致了数据库几行数据发生了变化）

statement.executeQuery方法用于向数据库发送查询语句，executeQuery方法返回代表查询结果的ResultSet对象

> CURD 操作-create

使用 executeUpdate(String sql)方法完成数据添加操作，示例操作：

```java
Stetement st = conn.createStatement();
String sql = "insert into user(...) values(...)";
int num = st.executeUpdate(sql);
if(num > 0){
    System.out.println("插入成功！！");
}
```

> CRUD 操作-delete

使用executeUpdate(String sql)方法完成数据删除操作，示例操作：

```java
Statement st = conn.createStatement();
String sql = "delete from user where id = 1";
int num = st.executeUpdate(sql);
if(num > 0){
    System.out.println("删除成功！");
}
```

> CRUD 操作-update

使用executeUpdate(String sql)方法完成数据修改操作，示例操作：

```java
statement st = conn.creatStatement();
String sql = "update user set name='' where name = ''";
int num = st.executeUpdate(sql);
if(num > 0){
    System.out.println("修改成功");
}
```

> CRUD 操作-read

使用executeQuery(String sql)方法完成数据查询操作，示例操作：

```java
Statement st = conn.createStatement();
String sql = "select * from user where id = 1";
ResultSet rs = st.executeUpdate(sql);
while(rs.next()){
    //根据获取列的数据类型，分别调用rs的相应方法映射到java对象中
}
```



