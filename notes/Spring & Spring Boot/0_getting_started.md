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

`@RestController` annotation tells Spring this code describes endpoint available over web.

`@GetMapping("/hello")` tells Spring `hello()` method handles requests sent to `http://localhost:8080/hello`.

`@RequestParam` tells Spring to expect `name` value in request, defaulting to "World" if missing.

## Build & Run

To build:

```sh
./gradlew
```

To run:

```sh
./gradlew bootRun
```

Spring Boot's embedded **Apache Tomcat** server acts as web server and is listening for requests on **localhost** port **8080**.

Point to `localhost:8080/hello?name=Steve` to verify app running successfully.
