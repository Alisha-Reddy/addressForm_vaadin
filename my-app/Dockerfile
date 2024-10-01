# Step 1: Use Java 17 as the base (most Vaadin projects use Java 17)
FROM openjdk:17-jdk-slim

# Step 2: Set the working directory inside the container
WORKDIR /app

# Step 3: Copy your entire project into the container
COPY . .

# Step 4: Build the project
# If you're using Maven:
RUN ./mvnw clean package

# If you're using Gradle:
# RUN ./gradlew build

# Step 5: Tell Docker to use port 8080 (where Vaadin runs by default)
EXPOSE 8080

# Step 6: Start your app
CMD ["java", "-jar", "target/myapp.jar"]
