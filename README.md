# Electronic Voting System

This is an electronic voting system built with Java and JavaFX. The application follows the MVC (Model-View-Controller) architecture.

## Prerequisites

- Java Development Kit (JDK) 11 or higher
- JavaFX SDK 11 or higher
- MySQL database server

## Installation

1. Install JDK from [Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) or [OpenJDK](https://jdk.java.net/)
2. Download JavaFX SDK from [here](https://gluonhq.com/products/javafx/)
3. Install MySQL server from [here](https://dev.mysql.com/downloads/mysql/)

## Database Setup

1. Create a database named `evoting`
2. Create tables using the following commands:

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL,
    password VARCHAR(50) NOT NULL,
    has_voted BOOLEAN DEFAULT FALSE,
    feedback TEXT
);

CREATE TABLE candidates (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    constituency VARCHAR(100) NOT NULL,
    votes INT DEFAULT 0,
    UNIQUE KEY unique_candidate_constituency (name, constituency)
);
```

## Configuration

1. Extract the JavaFX SDK to a location on your computer
2. Set the environment variable `PATH_TO_FX` to point to the JavaFX SDK lib directory
   - Windows: `set PATH_TO_FX=path\to\javafx-sdk\lib`
   - Mac/Linux: `export PATH_TO_FX=path/to/javafx-sdk/lib`

## Running the Application

1. Open a command prompt/terminal in the project directory
2. Run the application using the provided batch file:
   ```
   .\run.bat
   ```

## Features

- User registration and login with OTP verification
- Candidate registration
- Vote casting by constituency
- View election results by constituency
- Feedback collection and reporting
- Dashboard with system statistics

## Architecture

This application follows the MVC (Model-View-Controller) pattern:

- **Model**: Handles data operations and business logic
- **View**: Provides the user interface using JavaFX
- **Controller**: Connects the model and view, handling user actions

## Credits

Developed as a mini-project for OOAD. 
