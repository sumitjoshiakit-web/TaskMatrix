# TaskMatrix
# TaskMatrix

> An Agile Project Management Platform for modern teams.

## Project Overview

TaskMatrix is an enterprise-oriented Agile Project Management application designed to help teams organize projects, manage tasks, collaborate with team members, and monitor project progress through a centralized workspace.

The application will provide a structured workflow for creating projects, assigning tasks, tracking status, managing priorities, and viewing detailed task information.

---

## Project Information

| Field             | Details                    |
| ----------------- | -------------------------- |
| Project Name      | TaskMatrix                 |
| Designated Track  | Agile Project Management   |
| Project Type      | Enterprise Web Application |
| Development Phase | Capstone Planning          |
| Repository        | Public GitHub Repository   |

---

## Tech Stack

### Frontend

* React.js
* Vite
* JavaScript
* Tailwind CSS
* Zustand
* React Router

### Backend

* Node.js
* Express.js

### Database

* MongoDB

### Development & Design Tools

* Git
* GitHub
* Figma
* draw.io

---

# Product Requirements Document

## 1. Problem Statement

Modern software teams need a centralized platform to manage projects, tasks, team members, deadlines, priorities, and progress.

Managing these activities across separate tools can make it difficult to maintain a clear view of project progress.

TaskMatrix aims to provide a unified workspace where teams can manage their Agile workflow from project creation to task completion.

---

# 2. Target Users

TaskMatrix is designed for:

* Project Managers
* Team Leaders
* Developers
* Designers
* QA Engineers
* Students working in development teams
* Small and medium-sized software teams

---

# 3. Core Features

## P0 — Mandatory MVP Features

### Authentication

* User registration
* User login
* Logout
* Protected application routes
* Basic user profile

### Project Management

* Create project
* View projects
* Update project
* Delete project
* Project details

### Task Management

* Create task
* Edit task
* Delete task
* Assign task to a team member
* Set task priority
* Set task status
* Set due date

### Project Board

Tasks will be organized into workflow columns:

* Backlog
* To Do
* In Progress
* Review
* Done

### Dashboard

The dashboard will provide:

* Total projects
* Total tasks
* Completed tasks
* Pending tasks
* Tasks by priority
* Recent activity

---

# P1 — Priority Features

## Team Management

* Add team members
* Remove team members
* View team members
* Assign tasks to members

## Task Details

Each task will contain:

* Title
* Description
* Status
* Priority
* Assignee
* Due date
* Labels
* Comments
* Activity history

## Search and Filtering

Users will be able to:

* Search tasks
* Filter by status
* Filter by priority
* Filter by assignee
* Sort by due date

---

# P2 — Stretch Features

* Drag-and-drop task management
* Activity timeline
* Notifications
* Dark mode
* Advanced analytics
* Project progress charts
* Role-based permissions
* Real-time collaboration
* Advanced reporting

---

# 4. Application Views

The initial application architecture will contain the following major views:

### Authentication

* Login
* Register

### Main Application

* Dashboard
* Projects
* Project Board
* Team Members
* Notifications
* Profile

### Details

* Project Details
* Task Details
* User Details

---

# 5. Project Workflow

```text
Authentication
      ↓
Dashboard
      ↓
Projects
      ↓
Select Project
      ↓
Project Board
      ↓
Create / Select Task
      ↓
Task Details
      ↓
Update Status / Priority / Assignee
      ↓
Task Completed
```

---

# 6. Task Status Workflow

```text
Backlog
   ↓
To Do
   ↓
In Progress
   ↓
Review
   ↓
Done
```

---

# 7. Database Collections

The planned MongoDB collections are:

* users
* projects
* tasks
* comments
* notifications

### Users

Stores user account and profile information.

### Projects

Stores project information and project members.

### Tasks

Stores task information, status, priority, assignee, and project reference.

### Comments

Stores comments associated with tasks.

### Notifications

Stores user-specific system notifications.

---

# 8. Mock API Endpoints

## Authentication

```text
POST   /api/auth/register
POST   /api/auth/login
POST   /api/auth/logout
GET    /api/auth/me
```

## Projects

```text
GET    /api/projects
POST   /api/projects
GET    /api/projects/:projectId
PUT    /api/projects/:projectId
DELETE /api/projects/:projectId
```

## Tasks

```text
GET    /api/projects/:projectId/tasks
POST   /api/projects/:projectId/tasks
GET    /api/tasks/:taskId
PUT    /api/tasks/:taskId
DELETE /api/tasks/:taskId
```

## Comments

```text
GET    /api/tasks/:taskId/comments
POST   /api/tasks/:taskId/comments
DELETE /api/comments/:commentId
```

## Users

```text
GET    /api/users
GET    /api/users/:userId
PUT    /api/users/:userId
```

## Notifications

```text
GET    /api/notifications
PUT    /api/notifications/:notificationId/read
```

---

# 9. Global State Management

Zustand will be used to manage important application-wide state.

Planned stores:

```text
Global Store
│
├── Auth Store
│   ├── user
│   ├── isAuthenticated
│   └── loading
│
├── Project Store
│   ├── projects
│   ├── activeProject
│   └── loading
│
├── Task Store
│   ├── tasks
│   ├── selectedTask
│   ├── filters
│   └── loading
│
├── Team Store
│   ├── members
│   └── selectedMember
│
└── UI Store
    ├── sidebar
    ├── modal
    └── theme
```

---

# 10. UI/UX Design

The initial wireframe will contain at least three major views:

### View 1 — Authentication Screen

Contains:

* Application logo
* Email field
* Password field
* Login button
* Register link

### View 2 — Main Dashboard

Contains:

* Sidebar navigation
* Top navigation
* Project summary
* Task statistics
* Recent tasks
* Project progress

### View 3 — Project / Task Details

Contains:

* Project information
* Task board
* Task cards
* Task details panel
* Assignee
* Priority
* Status
* Comments

Figma Design File:

> Add the public Figma link here after completing the wireframes.

---

# 11. System Architecture

The system will follow a layered full-stack architecture:

```text
User
 ↓
Frontend Application
 ↓
API Layer
 ↓
Backend Services
 ↓
Database
```

The frontend will communicate with the backend through REST API endpoints.

The backend will handle authentication, project management, task management, comments, users, and notifications.

MongoDB will store application data using separate collections.

---

# 12. State Architecture

The frontend global state will be divided into independent stores:

```text
Application
│
├── Authentication
├── Projects
├── Tasks
├── Team
└── UI
```

This structure keeps application state modular and makes the system easier to maintain as the project grows.

---

# 13. Planned Architecture Documents

The repository will contain:

```text
docs/
├── architecture/
│   ├── system-architecture.png
│   └── state-tree.png
│
└── wireframes/
    └── figma-link.txt
```

---

# 14. Development Priorities

| Priority | Area                    | Status  |
| -------- | ----------------------- | ------- |
| P0       | Authentication          | Planned |
| P0       | Project Management      | Planned |
| P0       | Task Management         | Planned |
| P0       | Project Board           | Planned |
| P0       | Dashboard               | Planned |
| P1       | Team Management         | Planned |
| P1       | Task Details            | Planned |
| P1       | Search & Filtering      | Planned |
| P2       | Drag & Drop             | Planned |
| P2       | Notifications           | Planned |
| P2       | Analytics               | Planned |
| P2       | Real-time Collaboration | Planned |

---

# 15. Current Sprint Deliverables

* [x] Project selected
* [x] Repository initialized
* [x] PRD prepared
* [ ] Figma wireframes
* [ ] ERD
* [ ] Frontend state tree
* [ ] Architecture diagram
* [ ] Architecture image added to README

---

# 16. Future Development Phases

### Phase 1

Build the core MVP.

### Phase 2

Implement advanced project, team, and task management.

### Phase 3

Add optimization, analytics, notifications, and collaboration features.

### Phase 4

Testing, deployment, performance optimization, and documentation.

---

## Project Status

**Planning & Architecture Phase**
