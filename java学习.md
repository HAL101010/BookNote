# java学习



1.方法的重载和重写



2.泛型

3.接口、接口新特性（有点像C++中的抽象类和纯虚函数）

4.集合

5.java继承的特点（不允许多继承）（但是可以实现多个接口）

6.多态

7.Lambda表达式

8.内部类、匿名内部类

9.Treeset、自然排序、比较器排序

10.三种集合遍历方式：普通for/增强for/迭代器

11.servlet类

12.javascript标签绑定事件的两种方式（通过标签中事件属性进行绑定、通过DOM元素属性绑定）

13.javascript两种类的定义方式

14.java三种集合（Array/Set/Map)

15.JSON数据交换格式

16.hashmap遍历方式

大量简单程序的练习

Mybatis框架（用于操作数据库，内部封装了JDBC）

ORM对象关系映射（指的是持久化数据和实体对象的映射模式）

JDBC频繁创建和销毁数据库连接会影响性能

javascript匿名函数、含可变参数函数

DOM文档对象模型

BOM浏览器对象模型

事件处理

类的定义和使用



## javaweb核心

1servlet





## jQuery学习



jQuery是一个javascript库，库中封装了很多预定义函数，可以简化javascript操作

jQuery对象和javascript对象不是同一类，不能互相调用方法，要转换才能使用对应的方法

$(JS的DOM对象) ：将JS对象转换为jQuery对象

jQuery对象[索引]

jQuery对象.get(索引)



jQuery绑定事件的两种方式

jQuery对象.on(事件名称,执行功能)

解绑事件

jQuery 对象.off(事件名称);



jQuery事件的切换

单独定义

链式定义



jQuery遍历方式(四种)

1.传统for

2.对象.each(function(index,ele)){执行功能});

3.$each(容器对象,function(index,ele)){

​		执行功能；

});

4.for of语句

for(ele of 容器对象){执行功能});



jQuery选择器

1.基本选择器(类似CSS)(重点掌握)

元素选择器$("元素名称")

id选择器$("#id属性值")

类选择器$(".class属性值")

2.层级选择器(后代选择器、子选择器、兄弟选择器)

3.属性名选择器、属性值选择器

4.过滤器选择器、表单属性选择器



jQuery DOM操作

1.操作文本

html()获取标签文本

html(value)设置文本内容()(解析标签)

2.操作对象

$("元素")

append(element)

appendTo(element)

remove()删除指定元素(自己删除自己)

empty()清空指定元素所有子元素

3.jQuery操作样式

addClass(value)

removeClass(value)

4.操作属性

attr(name,[value])获得/设置属性的值

prop(name,[value])获得/设置属性的值(一般用于设置单选框和下拉列表)



## AJAX



异步的javascript和XML

用于实现异步更新网页

核心对象：XMLHttpRequest,用于在后台与服务器交换数据，可以在不加载整个网页的情况下，对网页的部分进行更新

打开链接

发生请求

处理响应

获得响应数据格式

jQuery实现AJAX:核心语法：get/post方式实现：$.get/post(url,[data],[callback],[type]);

url:请求资源路径

data:发送给服务器端的请求参数，格式可以是键值对，也可以是JS对象

callback:当请求成功后的回调参数，可以在函数中编写我们的逻辑代码

type预期的返回数据的类型，取值可以是xml,html,js,json,text等

jQuery通用方式实现AJAX

核心语法：$.ajax({name:value,name:value,...});

url:请求资源路径

async：是否异步，true or false

data：发送到服务器的数据，键值对或js对象

type：请求方式，get或post等

datatype预期返回值类型

success:请求成功时回调函数

error:请求失败时回调函数





JSON处理

JSON一种轻量级数据交换格式，层次简洁，易于阅读和理解，也易于计算机的解析

对象类型、数组/集合类型，混合类型

常用方法：

stringify(对象)

将指定对象转换为JSON格式字符串

parse(字符串)

将JSON字符串解析为对象

JSON转换工具(使Java中也可以使用JSON)：Jackson(就是一个jar包)SpringMVC转换默认使用jackson

其他重要jar包：log4j/mybatis/mysql



## BootStrap学习

响应式布局，偏移动设备

引入bootstrap.js前要先引入jquery.js

.container固定宽度,支持响应式布局的容器

.container-fluid100%宽度,占据全部viewpoint的容器



栅格网格系统



## Vue学习

Vue是一套构建用户界面的渐进式前端框架

只关注视图层

核心作用：响应数据的绑定和组合的视图组件



## Maven

作用：依赖管理，项目构建

项目对象模型(POM)

mvnrepository.com(查jar包)

很好用

常用命令

mvn -v版本

mvn help:system

mvn compile编译

mvn clean清理

mvn test测试

mvn package打包

mvn install将项目安装到本地仓库

mvn也可以直接用插件创建模板工程

创建java工程：quickstart

创建web工程：web



依赖管理

依赖就是项目运行需要的jar包

依赖的传递性

直接依赖和间接依赖

当依赖传递时出现冲突问题，遵循路径优先和声明优先













# Spring



由EJB思想发展而来

AOP思想

工厂模式——Spring由工厂模式逐步抽象得到

IOC控制反转，Spring反向控制应用程序所需要的资源

高内聚低耦合

资源交给工厂，由工厂交给应用程序



适合交给容器管理的bean

表现层对象(servlet)

业务层对象(service)

数据层对象(dao)

工具对象

不适合交给容器管理的bean

封装实体的域对象(domain/entity)



资源交给bean管理后不用new了

bean创建对象会自动调用无参构造方法



bean实例化方式：

1.构造方法

2.静态工厂(了解)

3.实例工厂与factorybean



IOC入门案列

1.maven导入spring坐标

2.编写业务层与表现层接口和实现类

3.编写spring配置文件

4.配置所需资源为spring控制的资源

5.表现层通过spring获取资源



beans标签用来配置spring中的资源

三个基本属性 id class name(name非必要，前两个必要)

bean可以创建 scope属性，用于控制bean创建的对象是否单例:propotype(非单例)singleton(单例)

bean的生命周期：init-method,destroy-method

bean的两个特殊属性：factory-bean，factory-method

定义bean对象创建方式，使用工厂创建对象



DI(依赖注入)，应用程序运行所需的资源由Spring为其提供，资源进入应用程序的方式称之为注入

set注入(主流，必须掌握)

简单类型，引用类型

(和IOC说的是同一件事，不过是从不同的角度)

构造器注入(了解)



强制依赖使用构造器进行

可选依赖使用setter注入进行

Spring框架倡导使用构造器，相对严谨

具体情况具体分析，两者都可使用

自己开发的模块推荐使用setter注入



bean的生命周期



自动装配

按名称

按类型



Spring学习路线

## 1.核心容器(IOC/DI)

IOC控制反转

由主动创建对象(new)变为外部(核心容器)提供对象

IOC容器负责对象的创建、初始化等工作，被创建和管理的对象在IOC容器中称为Bean



DI(依赖注入)

在IOC容器内将有依赖关系的bean进行关系绑定



两个思想的最终目标都是充分解耦



Ioc入门案列

1.导入Spring坐标

2.定义Spring管理的类、接口

3.创建Spring配置文件，配置对应Bean作为Spring管理bean(bean的id不要重复)

4.初始化Ioc容器(Spring核心容器/Spring容器)，通过容器获取bean



DI入门案列

1.删除使用new形式创建对象的代码

2.提供依赖对象对应的set方法(给容器提供)

3.在配置文件中配置service与dao之间的关系



bean的别名配置

bean可以通过name属性定义多个别名，使用,、;或空格隔开

Spring默认bean是单例的，要想非单例要用scope()作用范围属性修改为非单例



务必掌握构造方法实例化bean和FactoryBean方法实例化bean



实例化Bean的三种方式

1.构造方法(bean类中什么都不写提供默认构造方法)

步骤:提供可访问(public)的构造方法,在配置文件中配置bean(id,class)

2.静态工厂实例化bean(早期用的很多)

步骤:写好静态工厂类(类中提供返回值为所需类的方法),配置bean标签(id,class(工厂类的class),还有factory-method)

静态工厂示例:

```java
public class BookDaoFactory {
    public static BookDao getBookDao() {
        return new BookDaoImpl;
    }
}
```

3.实例工厂与FactoryBean

实例工厂和静态工厂差不多，但是没有static

```java
public class BookDaoFactory {
    public BookDao getBookDao() {
        return new BookDaoImpl;
    }
}
```

使用实例工厂要多加一行，因为要先有一个实例工厂对象

两行Bean,一行是实例工厂Bean，还有一行是实例工厂要造的bean(bean中只用写id,factory-method,factory-bean而不需要写class)

实例化bean的第四种方式:FactoryBean





依赖注入四种方式

1.setter方法(引用类型) 

set方法，pro标签

name ref

2.setter方法(简单类型) name value

3.构造方法(构造器)(引用类型)

构造方法，con标签

name=形参 ref

4.构造方法(简单类型)

根据bean需要数据的不同又分成两种情况

1.引用类型

2.简单类型



依赖自动装配(只适用于对引用类型依赖注入)

<bean> 标签中autowire



集合注入

List

Set

Map

Properties

pro标签中写数据类型标签，数据类型标签中写值



数据源对象管理



加载properties文件

1.开启context命名空间

2.使用context命名空间加载properties文件

3.value使用属性占位符${}读取properties文件中的属性值



核心容器总结

Beanfactory是IoC容器顶层接口，使用BeanFactory初始对象时bean延迟加载

ApplicationContext接口是Spring容器的核心接口，初始化时bean立即加载



## 注解开发

1.注解开发定义Bean

(1)使用@Component定义Bean

(2)核心配置文件中通过扫描组件扫描加载Bean

补充:Spring提供了@Component注解的三个衍生注解

@Controller:用于表现层Bean的定义

@Service:用于业务层Bean的定义

@Repository:用于数据层Bean的定义



2.纯注解开发

Spring3.0升级了纯注解开发模式，使用java类替代配置文件

配置文件的结构转换为@Configuration

配置文件中的扫描变化为@ComponentScan()

配置类中什么都不用写

读配置文件格式也改变为

```java
ApplicationContext ctx = new AnnotationConfigApplicationContext(SpringConfig.class)
```



@Configuration注解用于设定当前类为配置类

@ComponentScan注解用于设定扫描路径，此注解只能添加一次，多个数据要采用数组格式



注解开发bean的作用范围与生命周期管理

bean作用范围

要改变作用范围在bean实现类上添加注解@scope

bean生命周期

要改变生命周期在bean实现类中写上初始与销毁方法，然后在对应方法上分别写注解@PostConstruct和@PreDestroy

要看到销毁方法效果需要主动提供关闭钩子或关闭容器



注解开发依赖注入(自动装配)

引用类型依赖注入

在需要装配依赖的类中加上@Autowired(按名称装配或按类型装配)，此时可以不用写set方法了，他会通过反射机制中的暴力反射加值

如果有多个相同类型的bean，可以用@Qualifier("指定名称")

注意@Qualifier注解一定要依赖@Autowired注解，不能删掉

简单类型依赖注入

使用@Value实现简单类型注入

如果要加载Properties文件，则需要在Config类上再加一个注解@PropertySource("指定文件")

@PropertySource注解加载properties文件，多文件要使用数组的方式，不支持通配符



第三方bean管理

使用独立的配置类用于管理第三方Bean

@Bean标签+方法(返回值为所需bean)

使用@import在核心配置类中加载该配置类(多个配置类用数组)



第三方bean依赖注入

简单类型@value

引用类型：自动装配，只需要为bean定义方法设置形参即可



## 2.整合mybatis

核心bean:SqlSessionFactory

Spring整合MyBatis有两种方式：注解和xml配置文件，快速开发通常选用注解

步骤：

1.两个新坐标

2.新加配置类MybatisConfig(扫描类型别名包、扫描映射包)

配置类再两个新添类:SqlSessionFactoryBean/MapperScannerConfigurer

固定格式：

```java
public class MybatisConfig {
    @Bean
    public SqlSessionFactoryBean sqlSessionFactory(DataSource dataSource) {
        SqlSessionFactoryBean ssfb = new SqlSessionFactoryBean();
        ssfb.setTypeAliasesPackage("org.example.domain");
        ssfb.setDataSource(dataSource);
        return ssfb;
    }

    @Bean
    public MapperScannerConfigurer mapperScannerConfigurer() {
        MapperScannerConfigurer msc = new MapperScannerConfigurer();
        msc.setBasePackage("org.example.dao");
        return msc;
    }
}
```

在原先SpringConfig类中导入就行了

```java
@Configuration
@ComponentScan("org.example")
@PropertySource("jdbc.properties")
@Import({JdbcConfig.class,MybatisConfig.class})
public class SpringConfig {
}
```







## 3.AOP

aspect orented programming 面向切面编程，一种编程泛式，指导开发者如何组织程序结构

作用：在不惊动原始程序设计的基础上为其进行功能增强

Spring理念：无侵入式

做无侵入式的功能加强



基本概念：

连接点：程序执行过程中的任意位置，粒度为执行方法、抛出异常、设置变量等

切入点：匹配连接点的式子（连接点包含切入点、切入点一定在连接点中）（要进行增强的方法）

通知：在切入点执行的操作，也就是共性功能

切面：描述通知与切入点的对应关系

放通知的类就是通知类



步骤：

1、导入坐标

2、制作连接点方法

3、制作共性功能（通知类与通知）

4、定义切入点

5、绑定切入点与通知的关系（切面）



AOP工作流程（代理模式）

1.启动Spring容器

2.读取所有切面***配置中***的切入点

3.初始化bean,判定bean对应的类中的方法是否匹配到任意切入点

* 匹配失败，创建对象
* 匹配成功，创建原始对象(目标对象)的代理对象

4.获取bean执行方法

* 获取bean，调用方法并执行，完成操作
* 获取bean是代理对象时，根据代理对象的运行模式运行原始方法与增强的内容，完成操作



AOP切入点表达式

切入点表达式：要进行增强的方法的描述方式



语法格式

描述方式一：描述接口或实现类的方法

```java
@Pointcut("execution(void org.example.dao.BookDao.update())")
```

```java
@Pointcut("execution(void org.example.dao.impl.BookDaoImpl.save())")
```

切入点表达式标准格式：

动作关键字(访问修饰符	返回值	包名.类/接口名.方法名(参数)	异常名)

访问修饰符：public/private等，可以省略

异常：可以省略



通配符

在AOP中可以使用通配符快速描述(多个)切入点

*：单个独立符号，可以独立出现，叶可以作为前缀或者后缀的匹配符出现

```java
execution(public * org.example.*.UserService.find*(*))
```

代表返回值任意，org.example包下任意包的UserService包中的以find开头的方法，一个任意参数

要注意一个星号代表一个任意

..：多个连续的任意符号，可以独立出现，常用于简化包名与参数的书写

```java
execution(void org.example..BookDaoImpl.save(..))
```

+：专用于匹配子类类型

```java
execution(* *..*Service+.*(..)
```



书写技巧

* 所有代码按规范开发
* 描述切入点通常描述接口，不描述实现类
* 访问控制修饰符针对接口开发均采用public描述(可省略)
* 返回值类型对于增删改类使用精准类型加速匹配，对于查询类使用*通配快速描述
* 包名尽量不使用..匹配，效率过低，通常对单个包用*描述或精准匹配
* 通常不使用异常作为匹配规则
* 灵活使用



AOP通知类型

AOP通知描述了抽取的共性功能，根据共性功能抽取的位置不同，最终运行代码时要将其加入到合理的位置

AOP通知共分为5种类型

* 前置通知

* 后置通知

* 环绕通知(重点，常用)（可以实现前两种效果）

  标准写法：

  ```java
  @Around("pointcut()")
      public Object aroundSelect(ProceedingJoinPoint pjp) throws Throwable {
          System.out.println("around before advice...");
          //表示对原始操作的调用
          Object ret = pjp.proceed();
          System.out.println("around after advice...");
          return ret;
      }
  ```

  必须用ProceedingJoinPoint对象对原始方法进行调用，否则不执行原始方法

  必须抛异常

  返回值为Object类型

* 返回后通知(了解)

* 抛出异常后通知(了解)



AOP通知获取数据

获取参数

对于Around方式用ProceedingJoinPoint，对于其他的通知方式用JoinPoint

获取返回值

获取异常



## 4.事务

1.开启注解式事务驱动

在SpringConfig中添加注解

```java
@EnableTransactionManagement
```

2.配置事务管理器

事务要用到数据源对象，因此写在JdbcConfig类中

平台事务管理器

3.添加事务，将事务的@Transactional配置到接口上

添加到对应service接口上，不要添加到实现类上





# SpringMVC

入门案例

1.先导入Springmvc坐标和servlet坐标

2.创建Springmvc控制器类(功能等同于servlet)(controller)

3.初始化SpringMVC环境(同spring环境)，设定Springmvc加载对应bean

4.初始化servlet容器，加载springmvc环境，并设置Springmvc处理的请求

大部分是一次性工作(重点注意servlet容器的配置类,需要重写里面的抽象方法)

```java
//4.定义一个servlet容器启动的配置类，在里面加载spring的配置
public class ServletContainerConfig extends AbstractDispatcherServletInitializer {
    //加载SpringMVC容器配置(注册然后return)
    @Override
    protected WebApplicationContext createServletApplicationContext() {
        AnnotationConfigWebApplicationContext ctx= new AnnotationConfigWebApplicationContext();
        ctx.register(SpringMvcConfig.class);
        return ctx;
    }
    //设置哪些请求归属SpringMVC处理(请求路径)
    @Override
    protected String[] getServletMappings() {
        return new String[]{"/"};
    }
    //加载Spring容器配置
    @Override
    protected WebApplicationContext createRootApplicationContext() {
        return null;
    }
}

```



只有如下需要多次工作：

1）定义处理请求的控制器类

2）定义处理请求的控制器方法，并配置映射路径(@RequestMapping)与返回json数据(@ResponseBody)

```java
@Controller
public class UserController {
    //2.2设置当前操作的访问路径
    @RequestMapping("/save")
    //2.3设置当前操作的返回值类型
    @ResponseBody
    public String save(){
        System.out.println("user save...");
        return "{'info':'springmvc'}";
    }
}
```



## 1.SpringMVC简介

Springmvc控制表现层bean(controller)

Spring控制业务层bean(service)和功能bean(datasource)



快捷键

alt+insert自动写getter和setter方法

ctrl+o自动重写(override)(子类重写父类方法)

## 2.请求

web应用主要处理的两个内容就是请求与响应



请求

使用postman帮助开发



请求路径

@RequestMapping（"路径"）

设置在控制器类上是访问前缀

设置在方法上是具体的访问路径



请求方式

get请求(内容在请求头中(URL地址传值,地址参数名与形参变量名相同，定义形参即可接受参数))

post请求(请求内容在请求体中(form表单传值))

post请求可以在servlet容器管理类中设置过滤器处理，get不行



请求参数

1.普通参数

请求参数名与形参名不同时可以通过@RequestParam(“参数名”)绑定参数关系

2.POJO参数

3.嵌套POJO参数

4.数组类型参数

5.集合类型参数

注意集合类型参数要加@RequestParam标签



6.(重点)json类型参数

json数组

步骤：

1)在pom文件中导入jackson坐标(用于json数据处理)

2)在Springmvc核心配置文件中加上注释@EnableWebMvc(开启后才有json数据转对象的功能)

3)postman发送json数据格式

4)在参数前加注释@RequestBody

json对象(pojo)

json数组(pojo)



小结:

URL传参，form表单传参用@RequestParam

json传参用@RequestBody



7.日期参数转换：@DateTimeFormat

Converter





## 3.响应

响应页面(servlet主要响应页面)

响应数据(异步提交主要响应数据)(数据又主要是json数据)



@ResponseBody注解

作用：

1)设置当前控制器方法响应内容为当前返回值，无需解析

2)设置当前控制器返回值作为响应体(类型转换器HttpMessageConverter,需要jackson坐标)

## 4.REST风格

Representtational State Transfer表现形式状态转换

书写简化，隐藏资源访问行为



按照REST风格访问资源时使用行为动作区分对资源进行了何种操作

GET

POST

PUT

DELETE



根据REST风格对资源进行访问称为RESTful



@PathVariable用于接收路径参数，使用（参数名称）描述路径参数

后期开发中，发送请求参数超过一个时，以json格式为主，因此@RequestBody应用较广



REST风格简化开发

@ResquestMapping路径提到类外

@ResponseBody提到类外

@ResponseBody和@Controller合二为一为@RestController

@ResquestMapping改为具体的@Get/Put/Post/DeleteMapping等，每种定义一个请求方法

## 5.SSM整合

流程

1.创建工程，导入所需依赖

tomcat运行插件

依赖冲突处理(scope标签)

2.SSM整合

* Spring

   * SpringConfig

     ```java
     @Configuration
     @ComponentScan({"org.example.service"})
     @PropertySource("classpath:jdbc.properties")
     @Import({JdbcConfig.class,MyBatisConfig.class})
     @EnableTransactionManagement
     public class SpringConfig {
     }
     ```

 * MyBatis

   * MyBatisConfig

     ```java
     public class MyBatisConfig {
         @Bean
         public SqlSessionFactoryBean sqlSessionFactory(DataSource dataSource){
             SqlSessionFactoryBean factoryBean = new SqlSessionFactoryBean();
             factoryBean.setDataSource(dataSource);
             factoryBean.setTypeAliasesPackage("org.example.domain");
             return factoryBean;
         }
         @Bean
         public MapperScannerConfigurer mapperScannerConfigurer(){
             MapperScannerConfigurer msc = new MapperScannerConfigurer();
             msc.setBasePackage("org.example.dao");
             return msc;
         }
     }
     ```

   * JdbcConfig

     ```java
     public class JdbcConfig {
         @Value("${jdbc.driver}")
         private String driver;
         @Value("${jdbc.url}")
         private String url;
         @Value("${jdbc.username}")
         private String username;
         @Value("${jdbc.password}")
         private String password;
     
         @Bean
         public DataSource dataSource(){
             DruidDataSource dataSource = new DruidDataSource();
             dataSource.setDriverClassName(driver);
             dataSource.setUrl(url);
             dataSource.setUsername(username);
             dataSource.setPassword(password);
             return dataSource;
         }
         
         //此处数据源对象不要用方法调，用Spring自动装配即可(否则就不是Spring,变成java代码互相调用了)
         @Bean
         public PlatformTransactionManager transactionManager(DataSource dataSource){
             DataSourceTransactionManager ds = new DataSourceTransactionManager();
             ds.setDataSource(dataSource);
             return ds;
         }
     }
     ```

   * jdbc.properties

     ```java
     jdbc.driver=com.mysql.cj.jdbc.Driver
     jdbc.url=jdbc:mysql://localhost:3306/ssm_db
     jdbc.username=root
     jdbc.password=hongyang@123
     ```

 * SpringMVC

   * ServletConfig

     ```java
     public class ServletConfig extends AbstractAnnotationConfigDispatcherServletInitializer {
         @Override
         protected Class<?>[] getRootConfigClasses() {
             return new Class[]{SpringConfig.class};
         }
     
         @Override
         protected Class<?>[] getServletConfigClasses() {
             return new Class[]{SpringMvcConfig.class};
         }
     
         @Override
         protected String[] getServletMappings() {
             return new String[]{"/"};
         }
     
         //过滤器(乱码处理)
         @Override
         protected Filter[] getServletFilters() {
             CharacterEncodingFilter filter = new CharacterEncodingFilter();
             filter.setEncoding("UTF-8");
             return new Filter[]{filter};
         }
     }
     ```

   * SpringMvcConfig

     ```java
     @Configuration
     @ComponentScan({"org.example.controller"})
     @EnableWebMvc
     public class SpringMvcConfig {
     }
     ```

3.功能模块

* 表与实体类
* dao(接口+自动代理)
* service(接口+实现类)
  * 业务层接口测试(整合Junit)

* controller
  * 表现层接口测试(PostMan)



第二部分：表现层数据封装

统一返回值形式



第三部分：异常处理



出现异常的常见位置及常见诱因：

* 框架内部抛出异常：使用不合规导致
* 数据层抛出异常：情况较为复杂，常见如sql语句写错、服务器访问超时、数据库故障
* 业务层抛出异常：因业务逻辑书写错误导致，如空指针异常，遍历书写操作导致的索引异常
* 表现层抛出的异常：数据收集、校验规则导致，如数据类型不匹配
* 工具类异常：因工具类书写不严谨不够健壮导致，如必要释放的连接长期未释放导致



所有的异常均抛出到表现层进行处理

为了解决表现层处理异常每个方法单独书写导致代码量大，可以使用AOP思想

SpringMVC异常处理器提供便捷解决方法

```java
@RestControllerAdvice//Rest风格异常处理
public class ProjectExceptionAdvice {
    @ExceptionHandler(Exception.class)
    public Result doException(Exception ex){
        System.out.println("异常处理");
        return new Result(11111,null,"发生异常");
    }
}
```



项目异常处理

项目异常分类及处理方案：

* 业务异常
  * 规范的用户行为产生的异常
  * 不规范的用户从未产生的异常
    * 处理方案：提醒规范用户操作

* 系统异常
  * 项目运行过程中可预计但是无法避免的异常
    * 处理方案：发送特定消息给运维，提醒维护
    * 记录日志

* 其他异常
  * 编程人员未预期到的异常
    * 处理方案：发送特定消息给运维，提醒维护
    * 记录日志



## 6.拦截器

资源分为静态资源和动态资源

静态资源:html/css/js/image

动态资源:

拦截器(Interceptor)是一种动态拦截方法调用机制，在SpringMVC中动态拦截控制器方法的执行

作用:

在指定的方法调用前后执行预先设定的代码

阻止原始方法的执行



拦截器与过滤器区别：

归属不同：Filter属于Servlet技术，而Interceptor属于SpringMVC技术

拦截内容不同：Filter对所有访问进行增强，Interceptor仅针对SpringMVC访问做增强(SpringMVC配置时在ServletInitConfig中设置的访问路径)







