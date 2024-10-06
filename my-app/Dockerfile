# Step 1: Use Java 17 as the base (most Vaadin projects use Java 17)
FROM maven:3.9.8-eclipse-temurin-21 AS build

# Step 2: Set the working directory inside the container
WORKDIR /my-app/my-app

# Step 3: Copy your entire project into the container
COPY my-app/. .



# Step 4: Change permission for mvnw
# RUN chmod +x mvnw

# Debugging step: List files to confirm mvnw exists
# RUN cd /app/my-app/my-app
RUN ls -la
# RUN cd /app/my-app 
# RUN ls -la /app/my-app/.mvn

# Step 5: Build the project
RUN mvn clean install -U
#RUN ./mvnw clean package 
 
FROM openjdk:21
COPY --from=build /my-app/target/my-app-0.0.1-SNAPSHOT.jar /app/app.jar

# Step 6: Tell Docker to use port 8080 (where Vaadin runs by default)
EXPOSE 8080

# Step 7: Start your app
CMD ["java","-jar","my-app.jar"]
