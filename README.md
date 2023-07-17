# APIAutomationAssignment

This project is created as my API Automation assignment for my Automation Tester Application at Assurity Consulting. The details on how I created, how to use, and what are the tools, libraries, etc. used in this project is written in this **README** document. 

## API Details
Based on the email sent, here are the API details:
- URI:  _https://api.tmsandbox.co.nz_
- Resource: _/v1/Categories/6327/Details.json_
- Parameter:
  - key: catalogue
  - value: _false_
 
## Acceptance Criteria
- Name = _"Carbon credits"_
- CanRelist = _true_
- The Promotions element with Name = _"Gallery"_ has a Description that contains the text _"Good position in category"_

## The Project Framework
The project is built using different tools and frameworks especially for API automation. Such tools are:
### Maven
Maven is a build automation tool used primarily for Java projects. I utilized this tool for the creation of project folder and for managing the dependencies. Here are the dependencies I used in the project:

```xml
<dependencies>
		<!-- https://mvnrepository.com/artifact/io.cucumber/cucumber-java -->
		<dependency>
			<groupId>io.cucumber</groupId>
			<artifactId>cucumber-java</artifactId>
			<version>7.11.2</version>
		</dependency>
		<!-- https://mvnrepository.com/artifact/io.cucumber/cucumber-junit -->
		<dependency>
			<groupId>io.cucumber</groupId>
			<artifactId>cucumber-junit</artifactId>
			<version>7.11.2</version>
			<scope>test</scope>
		</dependency>
		<!-- https://mvnrepository.com/artifact/io.rest-assured/rest-assured -->
		<dependency>
			<groupId>io.rest-assured</groupId>
			<artifactId>rest-assured</artifactId>
			<version>5.3.0</version>
			<scope>test</scope>
		</dependency>
		<!-- https://mvnrepository.com/artifact/org.json/json -->
		<dependency>
			<groupId>org.json</groupId>
			<artifactId>json</artifactId>
			<version>20230227</version>
		</dependency>
	</dependencies>
```

### Cucumber 
Cucumber is a software tool that supports behavior-driven development. I used this as the base framework of my project by utilizing the feature file, step definition and test runner class.
- Feature file
 <img width="131" alt="image" src="https://github.com/ajabarentos/APIAutomationAssignment/assets/129655196/69b55e0e-a702-4cb1-a8d1-0ec3a14a8261">

- Step Definition class
 <img width="161" alt="image" src="https://github.com/ajabarentos/APIAutomationAssignment/assets/129655196/da58a684-dfbf-4a3a-a866-f66725eea42a">

- Test Runner class
 <img width="157" alt="image" src="https://github.com/ajabarentos/APIAutomationAssignment/assets/129655196/b858b125-1481-47f5-9292-fab0ab9d1c3c">  

### Rest Assured
It is a Java-based library that is used to test REST Web Services. I chose this library for the actual automation testing of the API. I utilized the **RestAssured** and **Response** class and their methods for the setup of URI, parameter, resource, method, etc. and also for validation.

```java
public void setBaseURI(String url) {
		RestAssured.baseURI = url;
	}
```
```java
public void sendGetRequest(String resource) {
		response = get(resource);
	}
```
```java
public void setParameter(String paramKey, String paramValue) {
		boolean parsedParamValue = Boolean.parseBoolean(paramValue);
		given().queryParam(paramKey, parsedParamValue);
	}
```
```java
public void validateStatusCode(int statusCode) {
		response.then().statusCode(statusCode);
	}
```





  


