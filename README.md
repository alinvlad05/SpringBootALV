# SpringBootALV
 
Application Configuration

Spring Boot applications supply a variety of powerful mechanisms for developers to dynamically configure and reconfigure their applications, even while the app is running. <br>
These mechanisms leverage the Spring Environment to manage configuration properties from all sources, including the following:<br>
• Spring Boot Developer Tools (devtools) global settings properties in the $HOME/.config/spring-boot directory when devtools is active.<br>
• @TestPropertySource annotations on tests.<br>
• properties attribute on tests, available on @SpringBootTest and the various test annotations for testing an application slice.<br>
• Command line arguments.<br>
• Properties from SPRING_APPLICATION_JSON (inline JSON embedded in an environment variable or system property).<br>
• ServletConfig init parameters.<br>
• ServletContext init parameters.<br>
• JNDI attributes from java:comp/env.<br>
• Java System properties (System.getProperties()).<br>
• OS environment variables.<br>
• A RandomValuePropertySource that has properties only in random.*.<br>
• Profile-specific application properties outside of the packaged jar (application-{profile}.properties and YAML variants).<br>
• Profile-specific application properties packaged inside the jar (application-{profile}.properties and YAML variants).<br>
• Application properties outside of the packaged jar (application.properties and YAML variants).<br>
• Application properties packaged inside the jar (application.properties and YAML variants).<br>
• @PropertySource annotations on @Configuration classes; note that such property sources are not added to the Environment until the application context is refreshed, which is too late to configure certain properties read before refresh begins, such as logging.* and spring.main.*.<br>
• Default properties specified by setting SpringApplication.setDefaultProperties.<br>


@Value<br>
The @Value annotation is perhaps the most straightforward approach to ingesting configuration settings into your code. Built around pattern-matching and the Spring Expression Language (SpEL), it’s simple and powerful.<br>
<br>
Using @ConfigurationProperties, a developer can define properties, group related properties, and reference/use them in a tool-verifiable and typesafe way.<br>
<br>
Autoconfiguration Report<br>
It’s a simple matter to produce the autoconfiguration report using the debug flag in one of several ways, owing to the flexibility of the JVM:<br>
• Executing the application’s jar file with the --debug option: java -jar bootapplication.jar --debug<br>
• Executing the application’s jar file with a JVM parameter: java -Ddebug=true -jar bootapplication.jar<br>
• Adding debug=true to your application’s application.properties file<br>
• Executing export DEBUG=true in your shell (Linux or Mac) or adding it to your Windows environment, then running java -jar bootapplication.jar<br>
