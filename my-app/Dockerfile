# Step 1: Use Java 17 as the base (most Vaadin projects use Java 17)
FROM openjdk:17-jdk-slim

# Step 2: Set the working directory inside the container
WORKDIR /app/my-app

# Step 3: Copy your entire project into the container
COPY . /app/my-app

# Step 4: Change permission for mvnw
# RUN chmod +x mvnw

# Debugging step: List files to confirm mvnw exists
# RUN ls -la /app/my-app
RUN ls -la /app/my-app/.mvn/wrapper

# Step 5: Build the project
RUN ./my-app/mvnw clean package 
 
# Step 6: Tell Docker to use port 8080 (where Vaadin runs by default)
EXPOSE 8080

# Step 7: Start your app
CMD ["java","-jar","target/my-app-1.0-SNAPSHOT.jar"]
