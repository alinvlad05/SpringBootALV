# SpringBootALV
 
Application Configuration

Spring Boot applications supply a variety of powerful mechanisms for developers to dynamically configure and reconfigure their applications, even while the app is running. 
These mechanisms leverage the Spring Environment to manage configuration properties from all sources, including the following:
• Spring Boot Developer Tools (devtools) global settings properties in the $HOME/.config/spring-boot directory when devtools is active.
• @TestPropertySource annotations on tests.
• properties attribute on tests, available on @SpringBootTest and the various test annotations for testing an application slice.
• Command line arguments.
• Properties from SPRING_APPLICATION_JSON (inline JSON embedded in an environment variable or system property).
• ServletConfig init parameters.
• ServletContext init parameters.
• JNDI attributes from java:comp/env.
• Java System properties (System.getProperties()).
• OS environment variables.
• A RandomValuePropertySource that has properties only in random.*.
• Profile-specific application properties outside of the packaged jar (application-{profile}.properties and YAML variants).
• Profile-specific application properties packaged inside the jar (application-{profile}.properties and YAML variants).
• Application properties outside of the packaged jar (application.properties and YAML variants).
• Application properties packaged inside the jar (application.properties and YAML variants).
• @PropertySource annotations on @Configuration classes; note that such property sources are not added to the Environment until the application context is refreshed, which is too late to configure certain properties read before refresh begins, such as logging.* and spring.main.*.
• Default properties specified by setting SpringApplication.setDefaultProperties.


@Value
The @Value annotation is perhaps the most straightforward approach to ingesting configuration settings into your code. Built around pattern-matching and the Spring Expression Language (SpEL), it’s simple and powerful.

Using @ConfigurationProperties, a developer can define properties, group related properties, and reference/use them in a tool-verifiable and typesafe way.

Autoconfiguration Report
It’s a simple matter to produce the autoconfiguration report using the debug flag in one of several ways, owing to the flexibility of the JVM:
• Executing the application’s jar file with the --debug option: java -jar bootapplication.jar --debug
• Executing the application’s jar file with a JVM parameter: java -Ddebug=true -jar bootapplication.jar
• Adding debug=true to your application’s application.properties file
• Executing export DEBUG=true in your shell (Linux or Mac) or adding it to your Windows environment, then running java -jar bootapplication.jar
