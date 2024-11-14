# Todo Application using Spring Boot

This is a Todo application built with Spring Boot, which supports storing data in either MongoDB or an in-memory database, depending on the configuration.

## Project Structure

- **Model**: Contains the `Todomodel` class with fields for `id`, `title`, and `description`.
- **Controller**: `TodoController` manages RESTful endpoints for CRUD operations on todo items.
- **Service**: `TodoService` provides a layer for business logic.
- **Data Access Layer (DAL)**:
  - `MongoRepo`: Uses MongoDB to store data.
  - `InMemory`: Uses a `HashMap` for in-memory storage.
  - `TodoRepo`: Interface that both `MongoRepo` and `InMemory` implement.
- **Configuration**: `TodoConfig` selects the storage type based on the `storage` variable in `application.properties`.

## Setup

1. **Prerequisites**:
   - Java 11+
   - MongoDB (optional if you are using in-memory storage)
   - Maven

2. **Configuration**:
   - Set the `storage` property in `application.properties` to either `mongo` (for MongoDB) or `memory` (for in-memory).
   - If using MongoDB, provide your MongoDB URL in `application.yml` under the appropriate configuration.

3. **Run the Application**:
   - Clone the repository:
     ```bash
     git clone <your-repo-link>
     ```
   - Navigate to the project directory:
     ```bash
     cd todo-using-springboot
     ```
   - Build and run the application:
     ```bash
     mvn spring-boot:run
     ```

4. **Endpoints**:
   - `GET /todos`: Retrieve all todos
   - `POST /todos`: Create a new todo
   - `PUT /todos/{id}`: Update a todo by ID
   - `DELETE /todos/{id}`: Delete a todo by ID

## Technologies Used

- **Spring Boot**
- **MongoDB** (optional)
- **In-memory storage** for testing purposes
- **Lombok** for generating boilerplate code

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
