# GETTING STARTED

Use [Spring Initializr](https://start.spring.io) to create "web" project. In **Dependencies** dialog add **Spring Web**. Hit **Generate** button, download zip and unpack.

Automatically contains **Spring Boot**, framework to easily make Spring app.

## Example

```java
package com.example.demo;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;

@SpringBootApplication
@RestController
public class DemoApplication {

    public static void main(String[] args) {
        SpringApplication.run(DemoApplication.class, args);
    }

    @GetMapping("/hello")
    public String hello(@RequestParam(value = "name", defaultValue = "World") String name) {
        return String.format("Hello %s!", name);
    }

}
```

In Spring's approach to building RESTful web services, HTTP requests are handled by controllers. These components are identified by `@RestController` annotation (shorthand of `@Controller` and `@ResponseBody`). It marks class as controller where every method returns domain object instead of view.

`@GetMapping("/hello")` tells Spring `hello()` method handles requests sent to `http://localhost:8080/hello`.

There are companion annotations for other HTTP verbs (e.g. `@PostMapping` for **POST**). All derive from `@RequestMapping`, which can serve as synonym (e.g. `@RequestMapping(method=GET)`).

`@RequestParam` binds value of query string param `name` into `name` param of `hello()`, defaulting to "World" if missing.

Example returns string, but can be custom object. Spring automatically converts obj to JSON (with **Jackson**).

`@SpringBootApplication` is convenience annotation for:

* `@Configuration`: Tags class as source of bean definitions for app context.
* `@EnableAutoConfiguration`: Tells Spring Boot to start adding beans based on **classpath** settings, other beans, and various property settings. E.g., if **spring-webmvc** is on classpath, flags app as web app and activates key behaviors, such as setting up `DispatcherServlet`.
* `@ComponentScan`: Tells Spring to look for other components, configurations, and services in **com/example** package, letting it find controllers.

 Spring Boot's `SpringApplication.run()` launches app.

## Build & Run

Can run app directly with Gradle or Maven. Or build single executable JAR file that contains dependencies, classes, and resources to run -- easier to ship, version, and deploy.

### Gradle

Run app with `./gradlew bootRun`. Or build JAR file with `./gradlew build` and run:

```sh
java -jar build/libs/rest-service-0.0.1.jar
```

### Maven

Run app with `./mvnw spring-boot:run`. Or build JAR file with `./mvnw clean package` and run:

```sh
java -jar target/rest-service-0.0.1.jar
```

### Test

Spring Boot's embedded **Apache Tomcat** server acts as web server and is listening for requests on **localhost** port **8080**.

Point to `localhost:8080/hello?name=Steve` to verify app running successfully.
