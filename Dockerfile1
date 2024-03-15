FROM maven:3.8.3-jdk-11-slim as build
WORKDIR /project
COPY . /project
RUN mvn clean package

FROM adoptopenjdk/openjdk11:jre-11.0.15_10-alpine
WORKDIR /app
RUN addgroup -g 1001 -S tecogroup 
RUN adduser -S teco -u 1001 
COPY --from=build /project/target/bmi-1.0.jar /app/bmi.jar
RUN chown -R teco:tecogroup /app
CMD java $JAVA_OPTS -jar bmi.jar

