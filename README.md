
# CRUD Operations with MySQL and FastAPI


In this project we have developed a complete application that performs CRUD (Create, Read, Update, Delete) operations on a MySQL database using Python. We have implemented wrapper functions for each CRUD operation and integrated these functions with the FastAPI framework to expose these operations as RESTful APIs.


## Table of Contents
- [Requirements](#requirements)
- [Installation](#installation)
- [Setup MySQL DB](#setup-mongodb)
- [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
- [Testing with Postman](#testing-with-postman)
- [Error Handling](#error-handling)
- [Contributing](#contributing)
## Requirements
- Python 3.7+
- MySQL Server
- FastAPI
- Uvicorn
- mysql-connector-python
## Installation
1. Clone the repository:
```shell
git clone https://github.com/ParasharAayush/CRUD_With_MySQL_FastAPI.git
cd CRUD_With_MySQL_FastAPI
```
2. Install the required packages:
```shell
pip install fastapi uvicorn mysql-connector-python
```



## Setup MySQL DB
1. Start your MySQL server.
2. Create a database named 'school'
```shell
CREATE DATABASE school;
```
3. Create the students table.
```shell
USE school;

CREATE TABLE students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    age INT NOT NULL,
    grade VARCHAR(10) NOT NULL
);
```

## Running the Application
1. Start the FastAPI application using Uvicorn:
```shell
uvicorn main:app --reload
```
2. The application will be available at http://127.0.0.1:8000
## API Endpoints
1. 'POST /students/': Create a new student
2. 'GET /students/': Get a list of all students
3. 'GET /students/{student_id}': Get details of a specific student by ID
4. 'PUT /students/{student_id}': Update a student's details
5. 'DELETE /students/{student_id}': Delete a student by ID


## Testing with Postman
### Create a Student
1. Open Postman.
2. Set the request type to 'POST'.
3. Enter the URL: 'http://127.0.0.1:8000/students/'.
4. Go to the 'Body' tab and select 'raw'.
5. Choose 'JSON' from the dropdown.
6. Enter the following JSON in the body:
```shell
{
  "name": "John Doe",
  "age": 20,
  "grade": "A"
}
```
7. Click 'Send'

### Get All students
1. Open Postman.
2. Set the request type to 'GET'.
3. Enter the URL: 'http://127.0.0.1:8000/students/'.
4. Click 'Send'.

### Get a Student by ID
1. Open Postman.
2. Set the request type to 'GET'.
3. Enter the URL: 'http://127.0.0.1:8000/students/1'.
4. Click 'Send'.

### Update a Student
1. Open Postman.
2. Set the request type to 'PUT'.
3. Enter the URL: 'http://127.0.0.1:8000/students/1'
4. Go to the 'Body' tab and select 'raw'.
5. Choose 'JSON' from the dropdown.
6. Enter the following JSON in the body:
```shell
{
  "name": "Jane Doe",
  "age": 22,
  "grade": "A+"
}
```
7. Click 'Send'

### Delete a Student
1. Open Postman
2. Set the request type to 'DELETE'
3. Enter the URL: 'http://127.0.0.1:8000/students/1'.
4. Click 'Send'.





## Error Handling
The application includes basic error handling to manage database connection issues and data validation errors. If an error occurs, the API will return an appropriate HTTP status code and error message.
## Contributing
Contributions are welcome! Please fork the repository and submit a pull request with your changes.
