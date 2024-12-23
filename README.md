# Habit Tracker Motivator

## Frontend - REACTJS & MATERIAL-UI

### Overview
This project provides a web-based Habit Tracker application with the following key features:

- **Login Page:** Allows users to sign in to their account.
- **Register Page:** Enables users to create a new account.
- **Dashboard Page:** The main page where users can:
  - Track their **Habits Progress**.
  - View and manage **Habit List** with CRUD functionality.
  - Receive **AI suggestions for habits** based on their preferences.
  - Update their **Profile**, including changing their name and password.
- **Light Mode & Dark Mode:** Toggle between light and dark themes for better user experience.

### Features

- **Login and Registration:** Users can sign in and register using their email and password.
- **Habit Progress:** Users can track their habit completion status.
- **CRUD Functionality:** Allows users to create, read, update, and delete habits.
- **Profile Management:** Users can change their name and password.
- **Theme Toggle:** Users can switch between light and dark mode.

### To Access the Frontend:

1. Navigate to the frontend folder:
   ```bash
   cd frontend/habit-tracker
2. Start the application:
   ```bash
   npm start

## Backend - NODEJS/EXPRESSJS & MYSQL

The backend of the Habit Tracker Motivator is built using Node.js and connects to a MySQL database for managing users and their habits. It provides a set of RESTful APIs to handle operations such as user creation, login, habit management, and profile updates.

### Features

- **User Authentication**: Users can create accounts, log in, and update their profiles.
- **Habit Management**: Users can create, update, retrieve, and delete habits.
- **MySQL Database**: All user and habit data is stored in a local MySQL database.

  

### To Access the Backend:

1. Navigate to the backend folder:
   ```bash
   cd backend
2. Start the application:
   ```bash
   node app.js
## API Functionality - POSTMAN API

### User API

| **Endpoint**                 | **Method** | **Request**                                                             | **Response**                                                                                         | **Description**                      |
|------------------------------|------------|-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------|--------------------------------------|
| `http://localhost:5000/api/users`                 | POST       | `{ "name": "John Doe", "email": "john@example.com", "password": "password123" }`  | `{ "message": "User created successfully", "userId": 12 }`                                           | Create a new user                   |
| `http://localhost:5000/api/users/login`           | POST       | `{ "email": "john@example.com", "password": "password123" }`              | `{ "message": "Login successful", "token": "<JWT>" }`                                                 | Login user                          |
| `http://localhost:5000/api/users/:userId`         | GET        | -                                                                       | `{ "name": "John Doe", "email": "john@example.com" }`                                               | Get user by ID                      |
| `http://localhost:5000/api/users/:userId`         | PUT        | `{ "name": "John Updated", "email": "john.updated@example.com" }`        | `{ "message": "User updated successfully" }`                                                        | Update user by ID                   |

### Habit API

| **Endpoint**                 | **Method** | **Request**                                                             | **Response**                                                                                         | **Description**                      |
|------------------------------|------------|-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------|--------------------------------------|
| `http://localhost:5000/api/habit`                 | POST       | `{ "userId": 1, "habitTitle": "Morning Jog", "startDate": "2024-12-23", "frequency": "Daily", "status": "Done" }` | `{ "message": "Habit created", "habitId": 4 }`                                                      | Create a new habit                  |
| `http://localhost:5000/api/habit/:userId`         | GET        | -                                                                       | `[ { "habit_id": 3, "user_id": 6, "habit_title": "Drink Water", "start_date": "2024-12-20", "frequency": "Daily", "status": "Not Done" } ]` | Get habits for a user                |
| `http://localhost:5000/api/habit/:userId`         | PUT        | `{ "status": "Not Done" }`                                              | `{ "message": "Habit status updated" }`                                                             | Update habit status                  |
| `http://localhost:5000/api/habit/:userId`         | DELETE     | -                                                                       | `{ "message": "Habit deleted" }`                                                                     | Delete a habit                       |

---


   
## AI Suggesting System - FLASK & SCIKIT-LEARN

The AI Suggesting System is a Flask app that generates habit recommendations based on a user's existing habits. The system compares habit categories using cosine similarity, providing the user with suggestions for new habits to adopt based on their current habits.

### Features

- **Habit Recommendations**: The app compares the categories of a user's habits to a predefined list of habit categories.
- **Cosine Similarity**: The app uses cosine similarity to determine the similarity between the user's habits and available habit categories.
- **Top 3 Suggestions**: The app returns the top 3 habit suggestions in JSON format.

### API Route

- **Generate Habit Suggestions**
  - **Method**: `GET`
  - **URL**: `http://127.0.0.1:5000/generate-habit-suggestions`
  - **Response**:
    ```json
    [
      {
        "habit_title": "Morning Meditation",
        "category": "Mental Health"
      },
      {
        "habit_title": "Daily Yoga",
        "category": "Physical Health"
      },
      {
        "habit_title": "Drink More Water",
        "category": "Physical Health"
      }
    ]
    ```

### To Access the Flask Code:

1. Navigate to the AI Service folder:
   ```bash
   cd ai_service
2. Run the Flask application:
   ```bash
   flask run

