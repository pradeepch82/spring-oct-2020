Day1    31-Oct-2020
====================

STS Download
============
https://download.springsource.com/release/STS4/4.8.1.RELEASE/dist/e4.17/spring-tool-suite-4-4.8.1.RELEASE-e4.17.0-win32.win32.x86_64.self-extracting.jar

Spring Distrubution 5.0
=======================
https://repo.spring.io/release/org/springframework/spring/5.0.2.RELEASE/


Develop a Stand alone Java Application to perform standard CRUD operations on Customer entity.

Customer
========
customerId (auto generated)
firstName
lastName
gender
email
address
city
state
dob

CustomerMainApp
         CustomerService
                 CustomerDao
                          CustomerMap



Develop a Stand alone Java Application to perform standard CRUD operations on Product entity.


Product
========
productId (auto genrated)
productName
price



ProductMainApp
         ProductService
                 ProductDao
                          ProductMap



Spring
=========


                            BeanFactory (I)   -------> Basic Container
                                 |
                                 |  XMLBeanFactory (C) 
                                 |
                        ApplicationContext(I)-------->Advanced Container
                                 |  
                                 |ClasspathXMLApplcationContext  -xml based 
                                 |AnnotationConfigApplicationContext --annotation based
                                 |
                     ServletWebApplicationContext----->Web Container

           
 










IOC  -Inversion of Contrl

DI :Mechamsim of initialzing the depencencies

  setter   ->    <property name="cs" ref="customerService">
  constructor -> <constructor-arg   name="cs" ref="customerService">
                          
                                                    
Spring Bean Life Cycle
==========================
1.Instantiation
2.Dependency Injection(setter/constructor)
3.Initialization   (init-method)
4.Service
5.Destruction      (destroy-method)

Spring Bean Scope : singletone|prototype|request|session


Day2 :1-Nov-2020
=================
Wiring :Associations of spring beans with each other


Autowiring :It is a mechanism of delagating the responsibilty of
            Associations of spring beans with each other to spring container                       


             auto-wire=no|byName|byType|constructor



Spring Bean Registration via Annotations
==========================================

We can register Spring Beans using any one of the below annotation


                              @Component
                              
                              
  @Controller                 @Service                @Repository
  
  

<bean  >  </bean>                  :@Component

<bean  auto-wire="">  </bean>       :@Autowire

<bean  init-method="">  </bean>     :@PostConstruct

<bean  destroy-method="">  </bean>  :@PreDestroy


CustomerMainApp
         CustomerService
                 CustomerDao
                          CustomerMap




beans.xml                => @Configuration
context:component-scan   => @ComponentScan




Day3 :7-Nov-2020
=================

CustomerMainApp
         CustomerService
                 CustomerDao
                          JdbcTemplate
                                 DataSource
                                         driver
                                         url
                                         username
                                         password       






https://o7planning.org/en/10683/create-a-shopping-cart-web-application-with-spring-boot-hibernate







driver
url
username
password



Day4 :10-Nov-2020
=================
              
                            Model       View     Controller
===========================================================
MVC1                       Java Bean    JSP      JSP
      
MVC2                       Java Bean    JSP      Servlet

MVC3                       Java Bean    JSP      Filter

MVC4                       Java Bean    JSP      Tag Handler



MVC2
======
Struts1.x
JSF1.x,2.x
Spring Web MVC



http://localhost:8080/spring-web-mvc/spring/hello
http://localhost:8080/spring-web-mvc/spring/welcome
http://localhost:8080/spring-web-mvc/spring/greet
http://localhost:8080/spring-web-mvc/spring/today





@Controller
public class DemoController {

	
	
	public DemoController() {
	
		System.out.println("Demo Controller created.....");
	
	}
	
	@RequestMapping(value="/hello",method = RequestMethod.GET)
	public @ResponseBody String hello() {
		return "HEllo World";
	}
	
	@RequestMapping(value="/greet",method = RequestMethod.GET)
	public @ResponseBody String greet() {
		return "Greet Every One";
	}
	
	@RequestMapping(value="/welcome",method = RequestMethod.GET)
	public @ResponseBody String welcome() {
		return "Welcome to Everyone";
	}
	
	@RequestMapping(value="/today")
	public  @ResponseBody String today() {
		return "Today is :"+new Date();
	}
		
}

=================


@RestController =@Controller +@ResponseBody



@RestController
public class DemoController {

	
	
	public DemoController() {
	
		System.out.println("Demo Controller created.....");
	
	}
	
	@RequestMapping(value="/hello",method = RequestMethod.GET)
	public String hello() {
		return "HEllo World";
	}
	
	@RequestMapping(value="/greet",method = RequestMethod.POST)
	public String greet() {
		return "Greet Every One";
	}
	
	@RequestMapping(value="/welcome",method = RequestMethod.DELETE)
	public String welcome() {
		return "Welcome to Everyone";
	}
	
	@RequestMapping(value="/today")
	public  String today() {
		return "Today is :"+new Date();
	}
		
}


==========================

@RequestMapping(value="/hello",method = RequestMethod.GET)
	 or
@Getmapping("/hello")


@RequestMapping(value="/hello",method = RequestMethod.POST)
	 or
@Postmapping("/hello")

@RequestMapping(value="/hello",method = RequestMethod.DELETE)
	 or
@Deletemapping("/hello")

@RequestMapping(value="/hello",method = RequestMethod.PUT)
	 or
@Putmapping("/hello")


Day5 :12-Nov-2020
=================

Restful Web API


http://localhost:8080/spring-cms-mvc/rest/customers      :GET    : get all customers
http://localhost:8080/spring-cms-mvc/rest/customers/101  :GET    : get customer with id 101
http://localhost:8080/spring-cms-mvc/rest/customers/101  :DELETE : delete customer with id 101
http://localhost:8080/spring-cms-mvc/rest/customers/101  :PUT    : update customer with id 101
http://localhost:8080/spring-cms-mvc/rest/customers      :POST   : add customer 





Path Varaibale
==============
http://localhost:8080/spring-cms-mvc/rest/customers/101

Request Param
==============
http://localhost:8080/spring-cms-mvc/rest/customers?customerId=101


PathVraible is supported by GET,PUT,DELETE,PATCH
RequestParam is supported by GET method




@ResponseBody  =>Convert Java Object to JSON  => Server to Client 
@RequestBody   =>Convert JSON to Java Object  => Client to Server


 jackson-annotations-2.9.0.jar
 jackson-core-2.9.8.jar
 jackson-databind-2.9.8.jar 


Day6 :19-Nov-2020
=================

Spring Web MVC CRUD Operations UI


Difference between applicationcontext and webapplicationcontext
=================================================================

https://codethataint.com/blog/difference-between-applicationcontext-and-webapplicationcontext/



To create a Root WebapplicationContext
============================================

<!-- rootapplicationcontext-->
<listener>
   <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
</listener>



Day7 :20-Nov-2020
=================

Normally if u want to develop Spring Web Applications.

1.Create a Project
2.Add jar files (compatbility version)
3.Configuration files (web.xml ,spring-servlet.xml)
4.Tomcat


What is Spring Boot?

Spring Boot is an open source Java-based framework used to create a Micro Service. It is developed by Pivotal Team. It is easy to create a stand-alone and production ready spring applications using Spring Boot. Spring Boot contains a comprehensive infrastructure support for developing a micro service and enables you to develop enterprise-ready applications that you can “just run”.



Spring Boot provides a good platform for Java developers to develop a stand-alone and production-grade spring application that you can just run. You can get started with minimum configurations without the need for an entire Spring configuration setup.




Advantages
===========
Spring Boot offers the following advantages to its developers −

Easy to understand and develop spring applications
Increases productivity
Reduces the development time

Goals
======

Spring Boot is designed with the following goals −

To avoid complex XML configuration in Spring
To develop a production ready Spring applications in an easier way
To reduce the development time and run the application independently
Offer an easier way of getting started with the application



Why Spring Boot?
=================
You can choose Spring Boot because of the features and benefits it offers as given here −

It provides a flexible way to configure Java Beans, XML configurations, and Database Transactions.

It provides a powerful batch processing and manages REST endpoints.

In Spring Boot, everything is auto configured; no manual configurations are needed.

It offers annotation-based spring application

Eases dependency management

It includes Embedded Servlet Container



1.Spring CLI
2.start.spring.io
3.STS




http://localhost:8080/actuator/info
http://localhost:8080/actuator/health



Spring Security
==============
Default username :user
Password  :will be generated on the console.

Customize Spring Security user and pwd
=========================================
spring.security.user.name=pradeep
spring.security.user.password=pradeep



Day8 :30-Nov-2020
=================
JPA (Java Persistance API)  :ORM Specification
================================================
Hibernate
ibatis
toplink


java.util.List (I) 
===================
ArrayList
LinkedList
Vector


Object oreinted data
====================

class Employee{
int id;
String name;
double salary;
}

Employee e=new Employee(101,"PRadeep",120000.00);


=============================================================
Employe
==============================================================
Id                Name             Salary
==============================================================
101               PRadeep          120000.00

MApping can be done in 2 ways
1.XML
2.Annotation



List<Student> getAllStudent(){
return new ArrayList<Student>();
return new LinkedList<Student>();
return new Vector<Student>();
}


ArrayList<Student> getAllStudent(){
return new ArrayList<Student>();
}


CRUDRepository
      |
      |
PagingAndSortingRepository
      |
      |
JPARepository

  

CustomerMainApp
         CustomerService
                 CustomerRepository
                          JPA
                             Hibernate
                                 JdbcTemplate
                                      DataSource
                                         driver
                                         url
                                         username
                                         password       


 

Day9 :5-Dec-2020
=================
Security
=========
JAAS -Java Authentication and Authorization Service


http status codes

400  :NOT FOUND
500  :Internal Server Error
200  :OK
405  :Method Not Allowed
401  :Unauthorized
403  :Forbidden 




Authentication Type
=====================
FORM  - Default From Spring Boot 2
BASIC - 
DIGEST



RAM      => ADMIN
RAHIM    => STUDENT
DAVID    => TEACHER




MongoDB



Day10 :5-Dec-2020
=================

Hibernate Relations
AOP
Google Auth Server










































