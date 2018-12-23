## 什么是Spring ##

- 轻量级的java开发框架
- 容器 降低耦合度

**核心:** 控制反转（IOC）和面向切面（AOP）

控制反转：
把new的工作交到了xml

### **怎么用** ###
>需要的jar

**Spring AOP：**Spring的面向切面编程，提供AOP（面向切面编程）的实现
**Spring Aspects：**Spring提供的对AspectJ框架的整合
**Spring Beans：**Spring IOC的基础实现，包含访问配置文件、创建和管理bean等，所有应用都用到。
**Spring Context：**在基础IOC功能上提供扩展服务，此外还提供许多企业级服务的支持，有邮件服务、任务调度、JNDI定位，EJB集成、远程访问、缓存以及多种视图层框架的支持。
Spring Context Support：Spring context的扩展支持，用于MVC方面。
**Spring Core：**Spring的核心工具包 ，其他包依赖此包
Spring expression：Spring表达式语言
Spring Instrument：Spring对服务器的代理接口
Spring Instrument Tomcat：Spring对tomcat连接池的集成
**Spring JDBC：** 对JDBC 的简单封装
Spring JMS：为简化jms api的使用而做的简单封装
Spring orm：整合第三方的orm实现，如hibernate，ibatis，jdo以及spring 的jpa实现
Spring oxm：Spring对于object/xml映射的支持，可以让JAVA与XML之间来回切换
**Spring test：**对JUNIT等测试框架的简单封装
Spring tx：为JDBC、Hibernate、JDO、JPA等提供的一致的声明式和编程式事务管理。
**Spring web:**包含Web应用开发时，用到Spring框架时所需的核心类，包括自动载入WebApplicationContext特性的类、Struts与JSF集成类、文件上传的支持类、Filter类和大量工具辅助类。
**Spring  webmvc：**包含SpringMVC框架相关的所有类。包含国际化、标签、Theme、视图展现的FreeMarker、JasperReports、 Tiles、Velocity、XSLT相关类。当然，如果你的应用使用了独立的MVC框架，则无需这个JAR文件里的任何类。
Spring webmvc portlet：Spring MVC的增强
Spring websocket：提供 Socket通信， web端的推送功能



#### XML文件的配置使用： ####

    <?xml version="1.0" encoding="UTF-8"?>
    <beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">
		
		<import resource="xxx.xml"/> <!-- 导入其他xml -->

	    <!--<bean id="user" class="com.learning.spring.two.User">-->
	        <!--<constructor-arg index="0" value="张三"/>-->
	        <!--<constructor-arg index="1" value="19"/>-->
	        <!--<constructor-arg index="2" ref="car"/>-->
	    <!--</bean>-->
	    <!--<bean id="car" class="com.learning.spring.two.Car">-->
	        <!--<property name="name" value="SUV"></property>-->
	        <!--<property name="color" value="white"></property>-->
	        <!---->
	    <!--</bean>-->
    </beans>	

#### Bean标签 ####



- **id属性：**用于指定Bean的名称，在Bean被依赖时使用，在获取Bean时使用等
- **name属性：**用于指定Bean的别名
- **class属性：**用于指定Bean的来源，即创建要创建的Bean的class类（需要全限定名）
- **parent属性:**子类Bean定义它所引用它的父类Bean。这时前面的class属性失效。子类Bean会继承父类Bean的所有属性，子类Bean也可以覆盖父类Bean的属性。注意：子类Bean和父类Bean是同一个Java类。
- **abstract属性（默认为”false”）：**用来定义Bean是否为抽象Bean。它表示这个Bean将不会被实例化，一般用于父类Bean，因为父类Bean主要是供子类Bean继承使用。
- **depends-on属性：**用于指定当前Bean的依赖Bean，强制指定的Bean在当前Bean初始化之前先完成初始化
- **init-method属性：**用于指定当前Bean的初始化方法，在Bean实例创建好后，首先会调用其指定名称的方法
- **destory-method属性：**用于指定当前Bean的销毁方法，在Bean即将被销毁之前会自动调用该属性指定的方法
- **lazy-init属性：**用于指定当前Bean的初始化时间，若值为true表示在初次调用时才会自动创建实例并初始化，false表示在IoC容器创建的时候就会完成创建和初始化
- **autowire属性：**用于指定当前Bean的依赖关系的自动注入方式，其有五个值：
 - byName值：表示通过id名称来自动匹配；
 - byType值：表示通过class指定的类型来自动装配；
 - constructor值：表示使用构造函数的参数进行自动装配（参数的类型匹配）；
 - autodetect值：表示自动进行选择匹配方式，首先进行constructor自动装配，若不存在构造方法则使用byType方式进行自动装配；
 - no值：表示不适用自动装配。
- **dependency-check属性：**用于指定Bean的依赖检查模式，检查依赖关系是否完整，与自动装配合用，
 - simple值：表示针对基本类型、字符串、集合进行依赖检查
 - object值：表示对引用对象进行依赖检查
 - all值：表示对基本类型、字符串、集合、引用对象全部进行依赖检查
 - none值：表示不进行任何依赖检查，默认情况。
- **scope属性**:用于指定当前Bean的创建模式，其有四个值：
 - singleton属性：表示为单例模式
 - prototype：表示原型模式
 - session：
 - request：

#### Bean的子元素 ####
- meta：元数据，当需要使用里面的信息时可以通过key获取

- lookup-method：获取器注入，是把一个方法声明为返回某种类型的bean但实际要返回的bean是在配置文件里面配置的

- replaced-method：可以在运行时调用新的方法替换现有的方法，还能动态的更新原有方法的逻辑

- constructor-arg：对bean自动寻找对应的构造函数，并在初始化的时候将设置的参数传入进去

- property：基本数据类型赋值

- qualifier：通过Qualifier指定注入bean的名称

　　

>单独配置

	<bean id="bs" class="包名.类的名字"/>相当于：Class.forName("package.Dog").newInstance();

	<bean class="xxx.yyy">
		<propertry name="name" value="xxx"/>属性注入
		<constructor-arg index="1" value="xxx"/> 构造器注入 同上作用一样
		<constructor-arg index="2" ref="bs"> 引入其他类
	</bean>

>根据包名进行注解

    <context:commponent-scan base-package="包名.类的名字"/>



#### 注解的方式  ####

**@Configuration：**用于定义配置类，可替换xml配置文件，被注解的类内部包含有一个或多个被@Bean注解的方法，这些方法将会被AnnotationConfigApplicationContext或AnnotationConfigWebApplicationContext类进行扫描，并用于构建bean定义，初始化Spring容器。可理解为用spring的时候xml里面的beans标签
**@Bean：**可理解为用spring的时候xml里面的bean标签
**@ComponentScan：**包名
**@ImportResource：**要引入的XML
**@Autowired ：**它可以对类成员变量、方法及构造函数进行标注，完成自动装配的工作。 通过 @Autowired的使用来消除 set ，get方法。
**@PropertySource：**注解加载指定的属性文件
	
**注意事项：**
@Autowired一定要等本类构造完成后，才能从外部引用设置进来。所以@Autowired的注入时间一定会晚于构造函数的执行时间。但在初始化变量的时候就使用了还没注入的bean，所以导致了NPE。若果在初始化其它变量时不使用这个要注入的bean，而是在以后的方法调用的时候去赋值，是可以使用这个bean的，因为那时类已初始化好，即已注入好了。

## AOP ##
主要实现：功能分离

**1. 静态代理**
> 使用接口实现
    
	public interface Sing {
		void start();
	}
>创建被代理类
	
    public class Singer implements Sing{
    	public void start(){
    		System.out.println("唱一首歌");
    	}
    }

>中间代理层

    public class ProxyEmcee implements Sing{
    	private final Sing sing;
    	public ProxyEmcee(Sing s){
    		this.sing = s;
    	}
    	public void start(){
    		System.out.println("有请这位歌手演唱");
    		sing.start();
    		System.out.println("有请下一位歌手");
    	}
    }
>测试

    public class Main {
    	public static void main(String[] args) {
    		Sing s = new ProxyEmcee(new Singer());
    		s.start();
    	}
    }


**2. 动态代理(JDK)** 继承InvocationHandler接口
> 使用接口实现
 
	public interface Sing {
		void start();
	}
>创建被代理类
	
    public class Singer implements Sing{
    		public void start(){
    			System.out.println("唱一首歌");
		}
    }
>中间代理层（继承InvocationHandler接口）

    public class ProxyEmcee implements InvocationHandler{
        private final Object o;

    public ProxyEmcee(Object o) {
        this.o = o;
    }

    @Override
    public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {
      		System.out.println("有请这位歌手演唱");
    		Object o = method.invoke(o, args);
    		System.out.println("有请下一位歌手")；
    		return o;
	}
    }


>测试

    public class Main {
    	public static void main(String[] args) {
    
    		Sing s = (Sing) Proxy.newProxyInstance(
    			Singer.class.getClassLoader(),new Class[]{Sing.class},
    			new ProxyEmcee(new Singer())
    		);
    		s.start();
    	}
    }
第一个参数：ClassLoader loader：它是类加载器类型

第二个参数：Class[] interfaces：指定newProxyInstance()方法返回的对象要实现哪些接口，没错，可以指定多个接口

第三个参数：handler主要就是对方法增加内容

**3. Cglib代理** （不需要接口）

>创建被代理类
	
    public class Singer {
    		public void start(){
    			System.out.println("唱一首歌");
		}
    }
>中间代理层（继承MethodInterceptor接口）
    
	public class CGRecordProxyGenerator implements MethodInterceptor {
    	@Override
    	public Object intercept(Object o, Method method, Object[] args, MethodProxy methodProxy) throws Throwable {
    		System.out.println("有请这位歌手演唱");
    		Object res = methodProxy.invokeSuper(o, args);
    		System.out.println("有请下一位歌手")； 
    		return res;
    	}
    }


>测试

    public class Main {
    	public static void main(String[] args) {
    		Singer o = (Singer) Enhancer.create(Singer.class, null, new ProxyEmcee());
    		o.start();
    	}
    }



使用xml

使用注解
**@Aspect:**

**@Before("execution(*.*.*.*(..))"):**




题外学习：
 	门面模式
	代理模式