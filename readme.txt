-----Contact Management Application

-Application Setup minimum requirement
	1) Java 1.8.0_161
	2) apache-maven-3.5.4
	3) Intellij Community version
	4) DB :- Here i have used H2 inmemory database, so external database required.
	
-How to import project in intellij and make ready to use steps
	1) once intellij editor opened you will able to see folder icon, click that icon,new window will popup, 
		give the base path of project which is downloaded from GIT & click ok.
	2) Give the .m2 repo setting.xml path in intellij, file-> setting->search for "maven", in this screen please give setting.xml file path (example:-C:\Users\Dell\.m2\settings.xml)
	3) for lambok Go to File > Settings > Plugins, Click on Browse repositories..., Search for Lombok Plugin, Click on Install plugin, Restart IntelliJ IDEA.
	4) At right hand side there is maven option, click on that, in that you will find contact-management under that there is Lifecycle,under that select clean and install at a same time
		and on right click you will able to see Run Maven Build click on that.
	5) It will download all the dependency, once build sucessfull application is ready to use.
	6) Open ContactManagementApplication.java file right click on that file and you will able to see Run ContactManagementApplication.main, click on that option it will start application in 
		inbuilt tomcat.
	7) Now applicationis ready to use.

-Featured used in this application are.
	1) Java 8
	2) Spring Boot 2
			-Sring REST -For rest controller
			-Spring Data - For data to store DAO side
			-swagger2 - kind of api to execute
			-Logger -logging
			-Security - to mentain security
			-Exception handling 
			-H2 in memory database

-Database Setup.
	In browser Open link, http://localhost:8080/h2-console , click on connect, under RUN execute below query one by one.
	
	DROP TABLE IF EXISTS CONTACT_DETAIL;

	CREATE TABLE CONTACT_DETAIL (
	  id INT AUTO_INCREMENT  PRIMARY KEY,
	  FIRST_NAME VARCHAR(250) NOT NULL,
	  LAST_NAME VARCHAR(250) NOT NULL,
	  EMAIL_ID VARCHAR(250) DEFAULT NULL,
	  PHONE_NUMBER LONG DEFAULT NULL,
	  USER_STATUS VARCHAR(40) NOT NULL
	);

	INSERT INTO CONTACT_DETAIL (FIRST_NAME, LAST_NAME, EMAIL_ID, PHONE_NUMBER, USER_STATUS) VALUES
	  ('Amit', 'mukta', 'ad@gmail.com', 2565859875, 'Active'),
	  ('Ramesh', 'Kale', 'rkale@gmail.com',57859658885, 'inactive'),
	  ('Sam', 'Fransis', 'samf2019@hotmail.com',8788948790,'Active'),
	  ('Ana', 'Mishra', 'amis@hotmail.com',8788948790,'inactive');
	  
	  
	Now DB is ready.
		
-Application Detail
	This application is for contact detail where we can perform CURD operation.
	
-Access API
	Here we are using swagger to execute all the CURD operation.
	Below is the Swagger url open it in Browser.
	http://localhost:8080/swagger-ui.html
	Under Contact Controller you will see all the API.(Please refer Swagger-Screen 1)	
	If we want add more data we can use POST API:- (Swagger-Screen 3 & 4) use below valid data.(use one at a time)
			{
				"firstName": "kumar",
				"lastName": "munde",
				"email": "kmunde@gmail.com",
				"phone": 1245896589,
				"status": "Active"
			}
			{
				"firstName": "Anil",
				"lastName": "katra",
				"email": "ak@gmail.com",
				"phone": 2356489658,
				"status": "Active"
			}
			
			{
				"firstName": "Amit",
				"lastName": "manak",
				"email": "am@gmail.com",
				"phone": 1256985686,
				"status": "Active"
			}
			
			{
				"firstName": "Sam",
				"lastName": "Fransis",
				"email": "sf@gmail.com",
				"phone": 1524785965,
				"status": "Inactive"
			}
			{
				"firstName": "Ram",
				"lastName": "Kale",
				"email": "rkale@gmail.com",
				"phone": 2456589658,
				"status": "Inactive"
			}
		As we have already entered data through POST API, so we can get all the deta by GET API, follow the steps given in (Swagger-Screen 5)
		If we want to get perticular data we can get by using id so for that we have GET API by ID, follow the steps given in(Swagger-Screen 6)
		If we want to update perticular data we can do it by using PUT API by valid data, below is the sample data,follow the steps given in (Swagger-Screen 7)
			{
			  "id": 3,
			  "firstName": "kumar",
			  "lastName": "munda",
			  "email": "km@gmail.com",
			  "phone": 1253659858,
			  "status": "Active"
			}
		If we want to update perticular data we can do it by using DELETE API by valid ID, follow the steps given in(Swagger-Screen 8)
	

	
	

	
