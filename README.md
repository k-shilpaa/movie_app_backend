# movie_app_backend
This is a microservices-based application designed to provide various functionalities related to movies, TV shows, user authentication, and payment processing. The application is built using Spring Boot and utilizes Eureka Server for service discovery, Gateway for API routing, and multiple microservices for different functionalities.

## Microservices
### 1. EurekaServer
EurekaServer is used for service discovery and registration. All microservices register themselves with EurekaServer upon startup, enabling dynamic routing and load balancing.
Technologies: Spring Cloud Netflix Eureka
Usage: Run EurekaServer as a standalone service before starting other microservices using `mvn spring-boot:run`.
### 2. Gateway
Gateway acts as an API gateway, routing incoming requests to appropriate microservices based on predefined routes and filters.
Technologies: Spring Cloud Gateway
Usage: Run Gateway as a standalone service. It will automatically register with EurekaServer.
### 3. MovieService
MovieService provides functionalities related to movies, such as CRUD operations, search, and recommendation.
Technologies: Spring Boot, Spring Data JPA
Usage: Run MovieService as a standalone service. It will automatically register with EurekaServer.
### 4. TvShowService
TvShowService provides functionalities related to TV shows, such as CRUD operations, search, and recommendation.
Technologies: Spring Boot, Spring Data JPA
Usage: Run TvShowService as a standalone service. It will automatically register with EurekaServer.
### 5. UserAuthentication
UserAuthentication handles user authentication and authorization, providing secure access to the application's functionalities.
Technologies: Spring Boot, Spring Security
Usage: Run UserAuthentication as a standalone service. It will automatically register with EurekaServer.
### 6. PaymentGateway
PaymentGateway integrates with payment processing services to handle transactions securely within the application.
Technologies: Spring Boot, Payment Processing SDK (e.g., Stripe, PayPal)
Usage: Run PaymentGateway as a standalone service. It will automatically register with EurekaServer.
Setup
Clone the Repository: Clone the repository to your local machine.

Build the Microservices: Navigate to each microservice directory (EurekaServer, Gateway, MovieService, TvShowService, UserAuthentication, PaymentGateway) and build them using Maven or Gradle.

Run EurekaServer: Start EurekaServer by running the appropriate command. Ensure it is running before starting other microservices.

Run Microservices: Start each microservice individually. They will register themselves with EurekaServer upon startup.

Access the Application: Access the application through Gateway's endpoint, typically `http://localhost:8080`.

Usage
Use API endpoints provided by Gateway to access various functionalities of the application.

## Static server
Features
Serve static images from a specified folder.
Access images via HTTP requests.
Install Dependencies: Navigate to the project directory and run npm install to install the necessary dependencies.

Configure Image Folder: Place your images in a folder within the project directory. By default, the server looks for images in the images folder. You can customize this by editing the IMAGE_FOLDER variable in the static-server file.

Run the Server: Start the server by running `serve-l:8090` command.

Access Images: Once the server is running, you can access the images by navigating to `http://localhost:8090/<image-name>` in your web browser or making HTTP requests programmatically.
