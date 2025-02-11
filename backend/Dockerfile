FROM maven AS package
WORKDIR /app
COPY . .
RUN mvn package
RUN mv ./target/*.jar ./App.jar

FROM openjdk:17-alpine
WORKDIR /build
COPY --from=package /app/App.jar ./
CMD ["java", "-jar", "App.jar"] 
