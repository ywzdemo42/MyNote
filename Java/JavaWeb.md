# JavaWeb

## 01.Tomcat 详解

## 02.Http讲解

## 03.Maven环境

## 04.IDEA中Maven的操作

## 05.Servlet

### 5.1 Servlet简介

- Servle就是sun公司开发动态web的一门技术

- Sun在这些API中提供一个借口叫做：Servlet，如果你想开发一个Servlet程序，只需要完成两个步骤：
  - 编写一个类，实现Servlet接口
  - 把开发好的Java类部署到web服务器中

**实现了Servlet接口的Java程序叫做，Servlet**

### 5.2 HelloServlet

#### 5.2.1编写Servlet的映射

为什么需要映射，因为我们写的是Java程序，但是要通过浏览器访问，而浏览器需要连接web服务器，**所以我们需要在web服务中注册我们写的Servlet，还需要给他一个浏览器能够访问的路径**

```java
//继承HttpServlet
public class ErrorServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req,HttpServletResponse resp) throws ServletException,IOException{
        //重写方法
    }
}
```



```xml
<!--注册Servlet-->
<servlet>
	<servlet-name>ErrorServlet</servlet-name>
    <servlet-class>com.ywz.servlet.ErrorServlet</servlet-class>
</servlet>
<!--Servlet请求路径-->
<servlet-mapping>
	<servlet-name>ErrorServlet</servlet-name>
    <url-pattern>/error</url-pattern>
</servlet-mapping>
```

#### 5.2.2配置Tomcat

### 5.3 Servlet运行原理

 ![image-20200731102147837](JavaWeb.assets/image-20200731102147837.png)

### 5.4 Mapping

1.一个Servlet可以指定一个映射路径

```xml
<servlet-mapping>
	<servlet-name>hello</servlet-name>
    <url-pattern>/hello</url-pattern>
</servlet-mapping>
```

2.一个Servlet可以指定多个映射路径

```mxl
<servlet-mapping>
	<servlet-name>hello</servlet-name>
    <url-pattern>/hello1</url-pattern>
</servlet-mapping>
<servlet-mapping>
	<servlet-name>hello</servlet-name>
    <url-pattern>/hello2</url-pattern>
</servlet-mapping>
```

3.一个Servlet可以指定通用映射路径

```xml
<servlet-mapping>
	<servlet-name>hello</servlet-name>
    <url-pattern>/hello/*</url-pattern>
</servlet-mapping>
```

4.指定一些后缀或者前缀等等

```xml
<servlet-mapping>
	<servlet-name>hello</servlet-name>
    <url-pattern>*.ywz</url-pattern> <!--"*"前面不能加映射路径-->
</servlet-mapping>
```

5.优先级问题

**指定了固有的映射路径优先级最高**，如果找不到则选择默认的处理请求

### 5.5 ServletContext（上下文）

web容器在启动的时候，它会为每个WEB程序都创建一个对应的ServletContext对象，它代表了当前的web应用；

```java
ServletContext servlerContext = this.getServletContext();
```

- **共享数据**   

  我在这个servlet中保存的数据，可以在另外一个servlet中拿到；

  1.Servlet参数设置

  2.Servlet参数取出

  

- 





 