## Running Eureka
Issue maven command to build eureka
`mvn package`
then use Spring boot command 
mvn spring-boot:run 
to run eureka on :http://localhost:8761

## Run Eureka as a server

run `java -jar server/target/feign-eureka-hello-server-0.0.1-SNAPSHOT.jar`

verify it is functioning at [http://localhost:7111](http://localhost:7111)

You should see `Hello World: HelloServer:myhostname:7111`

## Run client to register it self with eureka

run `java -jar client/target/feign-eureka-hello-client-0.0.1-SNAPSHOT.jar`

verify it is functioning at [http://localhost:7211](http://localhost:7211)

You should see `Hello World: HelloServer:myhostname:7111`


## See round robin load balancing in action

run `java -jar server/target/feign-eureka-hello-server-0.0.1-SNAPSHOT.jar --server.port=7112`

Go back to [http://localhost:7211](http://localhost:7211) and you should see both ports `7111` and `7112` in the output after a minute or two as you keep refreshing.
