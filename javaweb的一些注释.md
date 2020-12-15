# 实验一



```java
  /*
              User        id  username    birthday
              record      id  username    birthday    ResultSetMetaData
                          1   king        2020-10-14
                          2   tom         2020-10-15  ResultSet

​                          Map<String,Object> rowMap(key = 列名, value=列值)
​                          列名转化成类的方法名，给当前属性赋值的方法,id=seiId,username=setUsername,birthday=setBirthday
*/

/*
            Integer id=rs.getInt("id");
            String username=rs.getString("username");
            java.sql.Date birthday=rs.getDate("birthday");

​            //封装成一个对象
​            User user=new User();
​            user.setId(id);
​            user.setUsername(username);
​            //转换
​            java.util.Date birthday1=new java.util.Date(birthday.getTime());
​            user.setBirthday(birthday1);*/
```

...arg	可变长数组

```java

//Connection connection = getConnection();
//System.out.println(connection);
 //读取配置文件
 InputStream in = Thread.currentThread().getContextClassLoader().getResourceAsStream("config/db.properties");
//输入流
 Properties properties=new Properties();//解析文件
 properties.load(in);
 String username=properties.getProperty("username");
 String password=properties.getProperty("password");
 String driver=properties.getProperty("driver");
 String url=properties.getProperty("url");*/
 //加载驱动
 Class.forName(driver);
 //获取连接

Class.forName("com.mysql.jdbc.Driver");
String   url="jdbc:mysql://localhost:3306/jsuserverTimezone=GMT%2B8&useUnicode=true&characterEncoding=UTF8&useSSL=true";
String username="root";
String password="123456";*/
Connection connection=DriverManager.getConnection(url,username,password);
System.out.println(connection);
```

```java
//获取给propertyName属性赋值的set方法 //setId
String methodName="set"+propertyName.substring(0,1).toUpperCase()+propertyName.substring(1);//substring(0,1)把id的i取出,toUpperCase转成大写
//对象获取自己类对应的字节码文件 Use.class user.getClass()
Method method=clazz.getMethod(methodName,propertyValue.getClass());
//调用setId方法给user对象赋值 user.setId(1)
method.invoke(bean,propertyValue);

//上面部分使用commons-beanutils-1.9.4.jar、commons-collections-3.2.2.jar、commons-logging-1.2.jar包
 BeanUtils.setProperty(bean,propertyName,propertyValue);
```

```java
//User user=new User();
//clazz user.class字节码文件
//Class<User> clazz=User.class;
```

# 实验二

urlPatterns:

getParameter(String s)

三目运算符：x>y?1:0

```java
if(x>y) 
    return 1; 
else 
    reutun 0;
```

onsubmit

```javascript
<script>
  function  validate() {
    var email=document.getElementById("email").value;
    var password=document.getElementById("password").value;
    /*alert(email);//显示一下
    alert(password);//显示一下*/
    return false;//false不提交，true提交
  }
</script>
```

script-验证信息（邮箱正则表达式）

```javascript
var pattern=
```

