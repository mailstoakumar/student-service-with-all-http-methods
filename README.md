# Student Management Service

This is a Spring Boot microservice for managing student records. The service provides RESTful APIs to add, retrieve, update, and delete student information.

## Project Structure

The project is organized into the following packages:

- **controller**: Manages HTTP requests and responses.
- **service**: Contains business logic for student operations.
- **repository**: Handles data persistence (in-memory for this example).
- **model**: Contains data models for the application.

## API Endpoints

The base URL for the endpoints is `http://localhost:9090/students`.

### Retrieve All Students

- **HTTP Method**: `GET`
- **Endpoint**: `/students`
- **Description**: Retrieves a list of all students.
- **Example Request**:
    ```http
    GET http://localhost:9090/students
    ```

### Retrieve a Specific Student

- **HTTP Method**: `GET`
- **Endpoint**: `/students/{id}`
- **Description**: Retrieves details of a specific student by ID.
- **Path Parameter**:
    - `id`: The ID of the student to retrieve.
- **Example Request**:
    ```http
    GET http://localhost:9090/students/1
    ```

### Add a New Student

- **HTTP Method**: `POST`
- **Endpoint**: `/students`
- **Description**: Adds a new student.
- **Request Body**:
    ```json
    {
        "name": "John Doe",
        "age": 20
    }
    ```
- **Example Request**:
    ```http
    POST http://localhost:9090/students
    Content-Type: application/json

    {
        "name": "John Doe",
        "age": 20
    }
    ```

### Update an Existing Student

- **HTTP Method**: `PUT`
- **Endpoint**: `/students/{id}`
- **Description**: Updates details of an existing student by ID.
- **Path Parameter**:
    - `id`: The ID of the student to update.
- **Request Body**:
    ```json
    {
        "name": "Jane Doe",
        "age": 22
    }
    ```
- **Example Request**:
    ```http
    PUT http://localhost:9090/students/1
    Content-Type: application/json

    {
        "name": "Jane Doe",
        "age": 22
    }
    ```

### Delete a Student

- **HTTP Method**: `DELETE`
- **Endpoint**: `/students/{id}`
- **Description**: Deletes a specific student by ID.
- **Path Parameter**:
    - `id`: The ID of the student to delete.
- **Example Request**:
    ```http
    DELETE http://localhost:9090/students/1
    ```

## Setup and Run

### Prerequisites

- Java 17 or higher
- Maven 3.6.0 or higher

### Steps to Run

1. Clone the repository:
    ```bash
    git clone https://github.com/mailstoakumar/student-service-with-all-http-methods.git
    ```
2. Navigate to the project directory:
    ```bash
    cd student-service
    ```
3. Build the project using Maven:
    ```bash
    mvn clean install
    ```
4. Run the application:
    ```bash
    mvn spring-boot:run
    ```
5. The application will start on `http://localhost:9090` (or the port you configured).

## Testing

The project includes unit tests for the service layer. To run the tests, use:

```bash
mvn test
