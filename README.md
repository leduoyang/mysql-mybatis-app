# Spring Boot with MySQL and MyBatis

## Overview
This project is a simple Todo application implemented using Spring Boot, Mybatis, and MySQL. The app allows users to create, update, delete, and view tasks.

## Features
- **Create Tasks**: Add new tasks to the todo list.
- **View Tasks**: Retrieve the list of tasks.
- **Update Tasks**: Modify the details of existing tasks.
- **Delete Tasks**: Remove tasks from the list.

### Key Components
- **Controller**: Handles HTTP requests and routes them to the appropriate service methods.
- **Service**: Implements the business logic.
- **Mapper**: MyBatis mappers for database operations.
- **Model**: Defines the structure of data entities.
- **Configuration**: Includes configurations such as database connection and MyBatis settings.

## Database Schema
The application uses a `task` table in MySQL. Below is the schema:

```sql
CREATE TABLE task (
    id BIGINT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    description TEXT,
    status ENUM('PENDING', 'IN_PROGRESS', 'DONE') DEFAULT 'PENDING',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);
```

## API Endpoints

### Base URL: `/api/v1/tasks`

| Method | Endpoint          | Description               |
|--------|-------------------|---------------------------|
| POST   | `/`               | Create a new task         |
| GET    | `/`               | Retrieve all tasks        |
| GET    | `/{id}`           | Retrieve a specific task  |
| Patch  | `/{id}`           | Update a task             |
| DELETE | `/{id}`           | Delete a task             |
