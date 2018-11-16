# MVC Basic

## Remark:
This practice is following [this](https://spring.io/guides/gs/serving-web-content/) website.
- 1.Create build.gradle file

- 3.Create a web controller
	- src/main/java/hello/GreetingController.java
	- @Controller
	- @GetMapping("/greeting")
	- @RequestParam binds the value of the query String parameter name into the name parameter of the greeting() method. This query String parameter is not required; if it is absent in the request, the defaultValue of "World" is used. The value of the name parameter is added to a Model object, ultimately making it accessible to the view template.

- 4.Add template
	- src/main/resources/templates/greeting.html
	- The implementation of the method body relies on a view technology, in this case Thymeleaf, to perform server-side rendering of the HTML. Thymeleaf parses the greeting.html template below and evaluates the th:text expression to render the value of the ${name} parameter that was set in the controller.

- 5.Add a Home Page
	- src/main/resources/static/index.html
	- The index.html resource is special because it is used as a "welcome page" if it exists, which means it will be served up as the root resource, i.e. at http://localhost:8080/ in our example.

- 6.Make the application executable
	- Application.java
	- @SpringBootApplication

- 7.Build an executable JAR
	- Run Command ```./gradlew build``` to build the JAR file
	- ```java -jar build/libs/gs-serving-web-content-0.1.0.jar``` to run the application locally

- 8.Test the Application locally
	- Go to [local address](http://localhost:8080/greeting)  http://localhost:8080/greeting
	- Or [Provide a name query string parameter](http://localhost:8080/greeting?name=User) with http://localhost:8080/greeting?name=User. 