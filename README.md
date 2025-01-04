# To-Do App (REST API)

## Description
This project is a simple To-Do List application built using Django Rest Framework (DRF) that provides RESTful APIs for managing tasks. The application supports task creation, retrieval, updating, and deletion, along with JWT-based authentication for secure access.

## Features
1. **User Authentication:**
   - Secure login and token generation using JWT.

2. **Task Management Endpoints:**
   - Create new tasks.
   - Retrieve all tasks.
   - Retrieve a specific task by its ID.
   - Update the status of a task.
   - Delete a task.

## Endpoints
### Authentication
- `POST /api/token/` 
  - Generate JWT tokens for authenticated access.
  - **Required Fields:** `username`, `password`

### Task Management
1. **Create a Task:**
   - `POST /api/tasks/`
   - **Request Body:**
     ```json
     {
       "title": "Task Title",
       "description": "Task Description"
     }
     ```
   - **Response:**
     ```json
     {
       "id": 1,
       "title": "Task Title",
       "description": "Task Description",
       "status": "pending"
     }
     ```

2. **Retrieve All Tasks:**
   - `GET /api/tasks/`
   - **Response:**
     ```json
     [
       {
         "id": 1,
         "title": "Task Title",
         "description": "Task Description",
         "status": "pending"
       }
     ]
     ```

3. **Retrieve a Specific Task:**
   - `GET /api/tasks/<id>/`
   - **Response:**
     ```json
     {
       "id": 1,
       "title": "Task Title",
       "description": "Task Description",
       "status": "pending"
     }
     ```

4. **Update a Task Status:**
   - `PUT /api/tasks/<id>/`
   - **Request Body:**
     ```json
     {
       "status": "in-progress"
     }
     ```
   - **Response:**
     ```json
     {
       "id": 1,
       "title": "Task Title",
       "description": "Task Description",
       "status": "in-progress"
     }
     ```

5. **Delete a Task:**
   - `DELETE /api/tasks/<id>/`
   - **Response:**
     ```json
     {
       "message": "Task deleted successfully."
     }
     ```

## Installation
### Prerequisites
- Python 3.8+
- pip
- Virtual Environment (optional but recommended)

### Steps
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd todo-app
   ```

2. Create a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Apply migrations:
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

5. Create a superuser for admin access:
   ```bash
   python manage.py createsuperuser
   ```

6. Start the development server:
   ```bash
   python manage.py runserver
   ```

## Testing the APIs
You can test the API endpoints using [Postman](https://documenter.getpostman.com/view/37271849/2sAYJ99yHK) or any other API testing tool. Import the provided Postman collection to quickly access all endpoints.

## Project Structure
```
.
├── todo_project/         # Main project folder
│   ├── settings.py       # Django settings
│   ├── urls.py           # URL routing
│   └── ...
├── tasks/                # Task app
│   ├── models.py         # Task model
│   ├── views.py          # Task views
│   ├── serializers.py    # DRF serializers
│   └── urls.py           # Task app URLs
├── requirements.txt      # Dependencies
├── manage.py             # Django management script
└── README.md             # Project documentation
```

## Dependencies
- Django
- Django Rest Framework
- djangorestframework-simplejwt

## Future Enhancements
1. Add user-specific tasks with role-based permissions.
2. Include search and filter functionality for tasks.
3. Add frontend support with React or Angular.

---
Feel free to contribute to this project by creating pull requests or reporting issues!

