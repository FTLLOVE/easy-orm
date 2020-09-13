# EASY-ORM

## 特性

- 无侵入式
- 强大的CURD
- 链式ORM
- 内置分页
- 支持MYSQL,Oracle多种数据库
- 配置简单
- 内置Bean
- 强悍的查询表达式

## 简单使用

> ##### 准备一个bean对象，以Student对象为例

```java
import java.io.Serializable;

public class Student implements Serializable {
	
	private static final long serialVersionUID = 1L;
		
   private int id;
   
	private String name;
	
	private int age;
	
	private int sex;
   
   // GET SET ....
	
}
```

### 增

```java
public void insertOne() throws Exception {
		Student student = new Student();
		student.setName("豆芽菜");
		student.setAge(26);
		student.setSex(1);
		mysqlDao.insert(student); // 需要在Spring容器中注入MYSQLDao这个Bean对象
}
```

### 删

> 删除id=1的学生对象

```java
public void deleteOne() throws Exception {
		Criteria criteria = new Criteria("id=?", 1);
		mysqlDao.delete(Student.class, criteria);
}
```

### 改

```java
public void updateOne() throws Exception {
		Criteria criteria = new Criteria("id=?", 1);
		Student student = new Student();
		student.setName("张三");
		mysqlDao.update(student, criteria);
}
```

### 未完待续。。。





