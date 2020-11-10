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



































