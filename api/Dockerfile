FROM maven:3-openjdk-11

WORKDIR .

RUN pwd

COPY src/ ./src/
COPY pom.xml	./pom.xml
#COPY lib ./lib

RUN mvn install -Dmaven.test.skip=true 

RUN mvn package -Dmaven.test.skip=true 


# surement du EXPOSE à faire ?
EXPOSE 8080:8080

# CMD ["java", "-jar", "target/code-with-quarkus-1.0.0-SNAPSHOT-runner.jar"]
CMD ["java", "-jar", "/target/tlcdemoApp-1.0.0-SNAPSHOT-runner.jar"]

