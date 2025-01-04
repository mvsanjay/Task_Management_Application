# Task Management Application using Raft Consensus Algorithm

This project is a distributed **Task Management Application** designed for enhanced task tracking and collaboration across teams. It employs the **Raft Consensus Algorithm** to ensure consistency and fault tolerance across nodes, with **MySQL** serving as the backend database. The system supports CRUD operations for task management and demonstrates core principles of distributed systems.

## Features

- **Distributed Architecture**: Implements the Raft Consensus Algorithm for fault tolerance and leader-based log replication.
- **Task Management**: Provides a full range of CRUD operations for managing tasks.
- **Data Consistency**: Ensures consistency across nodes in the distributed system.
- **Scalability**: Built on a microservices architecture for seamless scalability and maintenance.
- **User-Friendly Interface**: Frontend for easy task interaction (React-based UI planned).
- **MySQL Backend**: Reliable and robust relational database for task data.

## Project Structure

- **main.py**: Streamlit-based frontend to interact with the backend via REST APIs.
- **raft_sql.go**: Go implementation of backend services, including Raft algorithm integration and MySQL CRUD operations.
- **task_manager.sql**: SQL schema file for setting up the MySQL database.
- **Documentation**:
  - **Task Management Application Design Document.pdf**: Detailed architecture and design document.
- **go.mod**: Tracks module path and project dependencies for Go.
- **go.sum**: Ensures integrity and consistency of Go dependencies.

## Architecture Overview

The application uses a **microservices architecture**:
- **Frontend**: React-based UI (Streamlit for current prototype).
- **Backend**: 
  - **Raft Consensus Algorithm** ensures leader election and log replication.
  - **MySQL** stores and manages task data.
- **Node Roles**:
  - **Leader**: Handles all write operations and replicates logs to followers.
  - **Followers**: Maintain replicas and serve as backups during leader failure.
  - **Candidate**: Initiates leader elections upon failure.
## Installation

### Prerequisites

- **Python**: Version 3.8 or higher
- **MySQL**: Version 8.x or compatible
- **Go**: Version 1.16 or higher
- **Streamlit**: Install via `pip install streamlit`

### Setup

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-name>
2. Set up MySQL:  
Import the provided schema for `task_manager`.
Update database credentials in `raft_sql.go`.
3. Initialize Go modules:
   ```bash
   cd backend
   go mod tidy
4. Run the backend:
   ```bash
   go run raft_sql.go
5. Launch the frontend:
   ```bash
   streamlit run main.py

## Usage
1. Start the backend services (raft_sql.go).  
2. Launch the frontend (main.py) to interact with tasks.  
3. Use the UI to:  
    - Create new tasks.  
    - View all tasks.
    - Update task details.  
    - Delete tasks.  

## Design Highlights
- **Schema**:
  - Tasks: `task_id`, `description`, `status`, `priority`, `created_at`, `updated_at`.
  - Users: `user_id`, `name`, `email`, `password_hash`.
  - Assignments: Links tasks to users for collaboration.
- **Raft Algorithm**:
  - Ensures consistency using log replication.
  - Manages leader election and handles node failures.
- **Testing**:
  - Unit tests for individual modules.
  - Integration tests for API endpoints.  


