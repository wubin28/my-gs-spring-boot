[Building an Application with Spring Boot](https://spring.io/guides/gs/spring-boot/)

# Run the application

To run the application, execute:

~~~~
./gradlew build && java -jar build/libs/gs-spring-boot-0.1.0.jar
~~~~

# What if the port 8080 is used

~~~~
lsof -n -i4TCP:8080
kill -9 <pid>
~~~~

# Check out the service

~~~~
$ curl localhost:8080
Greetings from Spring Boot!
~~~~

# Add production-grade services

There is also a /shutdown endpoint, but it’s only visible by default via JMX. To enable it as an HTTP endpoint, add endpoints.shutdown.enabled=true to your application.properties file.

It’s easy to check the health of the app.

~~~~
$ curl localhost:8080/health
{"status":"UP","diskSpace":{"status":"UP","total":397635555328,"free":328389529600,"threshold":10485760}}}
~~~~

You can try to invoke shutdown through curl.

~~~~
$ curl -X POST localhost:8080/shutdown
{"message":"Shutting down, bye..."}
~~~~

