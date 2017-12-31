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
