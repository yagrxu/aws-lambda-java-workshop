FROM maven:3-amazoncorretto-17 as builder

COPY ./pom.xml ./pom.xml
RUN mvn dependency:go-offline -f ./pom.xml

COPY src ./src/
RUN mvn clean package && mv target/store-spring-1.0.0.jar store-spring.jar

EXPOSE 80
ENTRYPOINT ["java","-jar","-Dserver.port=80","/store-spring.jar"]
