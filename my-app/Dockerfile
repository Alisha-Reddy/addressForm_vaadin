# Step 1: Use Java 17 as the base (most Vaadin projects use Java 17)
FROM openjdk:21-jdk-slim

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
RUN ./mvnw clean package 
 
# Step 6: Tell Docker to use port 8080 (where Vaadin runs by default)
EXPOSE 8080

# Step 7: Start your app
CMD ["java","-jar","target/my-app-1.0-SNAPSHOT.jar"]
