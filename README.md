# mimi-trello-clone
# Trello clone 
Web app to manage tasks and projects.

## Image Sample
![image](https://github.com/abhay5aa/mimi-trello-clone/assets/145688425/7073a644-46f3-46e7-ad0d-a833e2adb4ea)



## How would your tables and apis change for the following scenarios. What tables and api 
## endpoints would you add? Which tables and api endpoints would need to be updated? 
## 1. If a user can create and edit stages for a particular board. For example instead of 
## Open > In Progress > Done if they want the stages of their task board to be Read > 
## Working > Reviewing > Completed 
## 2. If users can comment on tasks 
## 3. How will you do error handling?

Scenario 1: If a user can create and edit stages for a particular board
Tables: In this scenario, you would need to introduce a new table to store the stages associated with a board. Your existing tables might include:
User: Stores user information.
Board: Stores information about boards.
Stage: Currently, you have predefined stages (e.g., Todo, Doing, Done). You might replace this with a new table like BoardStage to allow users to create and edit stages specific to their boards.
API Endpoints: New API endpoints would be required to support the creation and editing of stages for a board. Existing API endpoints might also need updates to reflect these changes. Here are examples of what you might need:
POST /api/boards/:boardId/stages: Create a new stage for a specific board.
PUT /api/boards/:boardId/stages/:stageId: Update an existing stage for a specific board.
GET /api/boards/:boardId/stages: Retrieve all stages for a specific board.
Scenario 2: If users can comment on tasks
Tables: To support comments on tasks, you would need to introduce a new table for comments. Your existing tables might include:
User: Stores user information.
Board: Stores information about boards.
Stage: Stores information about stages.
Task: Stores information about tasks.
Comment: This new table would store comments made by users on tasks.
API Endpoints: New API endpoints would be required to support commenting on tasks, and the existing endpoints might need updates. Here are examples of what you might need:
POST /api/tasks/:taskId/comments: Create a new comment on a specific task.
GET /api/tasks/:taskId/comments: Retrieve all comments for a specific task.
PUT /api/tasks/:taskId/comments/:commentId: Update an existing comment on a specific task.
DELETE /api/tasks/:taskId/comments/:commentId: Delete a comment on a specific task.
Scenario 3: Error Handling
Error handling is an essential aspect of any application. You should consider adding standardized error responses to your API to provide clear feedback to the client. Here are some common practices:
Use appropriate HTTP status codes (e.g., 400 for client errors, 500 for server errors).
Include error messages and codes in the response payload to help clients identify the issue.
Implement global error handling middleware that catches unhandled errors and formats responses consistently.
Log errors on the server for debugging purposes.
Consider rate limiting and authentication errors as well.
For example, you might have a standardized error response format like:
{
  "error": {
    "code": "ERR001",
    "message": "Invalid input data",
    "details": "The 'title' field is required."
  }
}


## Features Built
- Register User
- Login User
- Home page
    - Display all user's boards
    - Feature to create new board
- Individual Board page
    - Display all user's lists and cards
    - Feature to edit board name on click of the board name
    - Feature to create new list and card
    - Feature to edit list or card name on click of list or card name
    - Feature to drag and drop cards within lists and between two lists
    - Modal feature to edit card name or add description to the card on click of edit icon in the card
- Navbar
    - Option to go to home page on click of the trello text
    - Option to logout

## Technology Stack
- HTML
- CSS
- Javascript
- React JS
- Node JS
- Express JS
- MongoDB

## Additional libraries used for frontend
- react-router-dom
- axios
- react-beautiful-dnd
- react-modal
- react-simple-snackbar
- react-icons

## Additional libraries used for backend
- dotenv
- cors
- jsonwebtoken
- bcryptjs
- decimal.js



