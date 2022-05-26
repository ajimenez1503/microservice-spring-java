# microservice-spring-java

Learn how to develop microservices in Java using Spring

Microservice will be used for customer registration.

The architecture of our system will be:
![img.png](img/architecture.png)

Ref:

- https://www.youtube.com/watch?v=1aWhYEynZQw
- https://github.com/amigoscode/microservices

# Steps

#### Installing Maven

```
sudo apt update
sudo apt install maven
mvn --version
```

#### Create the project
```
mvn archetype:generate -DgroupId=com.example.app -DartifactId=microservice-spring-java -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false
```
- Create customer

#### Run docker compose:
```
docker-compose -f docker-compose.yml up -d
```
- Open pgadmin `http://localhost:5050/`
  - Add a server
  - Create the customer database

### Run the microservice customer
- Run the microservice using intellij
- Post a customer
```
curl -X POST \
  http://localhost:8080/api/v1/customers \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'postman-token: 3b6a3676-66e9-e61f-5a62-f98899b27ebc' \
  -d '{
	"firstName":"Antonio",
	"lastName":"Jimenez",
	"email": "antonio@gmail.com"
}'
```