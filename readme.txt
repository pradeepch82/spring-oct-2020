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
3.Initialization
4.Service
5.Destruction


Spring Bean Scope : singletone|prototype|request|session





Wiring :Associations of spring beans with each other

Autowiring :It is a mechanism of delagating the responsibilty of
            Associations of spring beans with each other to spring container                       


             auto-wire=no|byName|byType|constructor




                              @Component
                              
                              
  @Controller                 @Service                @Repository
  
  





Customer c1=new Customer();

c1.setId(101);
c1.setId(101);
c1.setId(101);
c1.setId(101);















