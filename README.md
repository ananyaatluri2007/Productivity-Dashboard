🚀 Productivity Dashboard API
A full-stack backend application built with Node.js, Express, and Sequelize (SQLite). This API allows users to manage tasks, track deadlines, and view productivity analytics through a secure dashboard.

🛠️ Tech Stack
Runtime: Node.js

Framework: Express.js

Database: SQLite (Relational)

ORM: Sequelize

Authentication: JWT (JSON Web Tokens)

Security: Bcrypt.js (Password Hashing)

✨ Key Features
1. Secure Authentication
Registration: Unique email and username validation.

Login: Password verification using Bcrypt and JWT generation.

Protection: Middleware ensures only authorized users can manage tasks or view stats.

2. Intelligent Task Management
Full CRUD: Create, Read, Update, and Delete tasks.

Search & Filter: Search tasks by title or filter by status (Pending, In Progress, Completed).

Automatic Overdue Detection: A custom Sequelize hook dynamically calculates if a task is overdue based on the current date and deadline.

3. Productivity Analytics
Real-time Stats: Calculates total tasks vs. completed tasks.

Completion Rate: Provides a percentage-based performance metric.

Priority Breakdown: Visualizes workload distribution (High, Medium, Low).

📂 Project Structure
Plaintext

productivity-api/
├── src/
│   ├── controllers/    # Logic for Auth, Tasks, and Dashboard
│   ├── middleware/     # JWT Authentication middleware
│   ├── models/         # Sequelize Models (User, Task)
│   ├── routes/         # API Endpoint definitions
│   └── app.js          # Main entry point
├── .env                # Environment variables
├── database.sqlite     # Local database file
├── seed.js             # Script to populate test data
└── package.json        # Dependencies and scripts
🚀 Getting Started
1. Installation
Clone the repository and install the dependencies:

Bash

npm install
2. Environment Setup
Create a .env file in the root directory:

Plaintext

PORT=3000
JWT_SECRET=your_secret_key_here
3. Seed the Database
Run the seed script to create a test user and dummy tasks:

Bash

node seed.js
4. Run the Server
Bash

npm run dev
🧪 API Endpoints
Auth
POST /api/auth/register - Create an account.

POST /api/auth/login - Get access token.

Tasks (Requires Bearer Token)
GET /api/tasks - List all tasks (includes isOverdue flag).

POST /api/tasks - Create a new task.

GET /api/tasks?search=Project - Search tasks.

Dashboard (Requires Bearer Token)
GET /api/dashboard/stats - View productivity analytics.
