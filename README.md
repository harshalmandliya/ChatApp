# ChatApp

A real-time chat application built with Spring Boot, WebSocket, and STOMP messaging protocol.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running the Application](#running-the-application)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [WebSocket Configuration](#websocket-configuration)


## Overview

ChatApp is a simple real-time chat application that allows multiple users to communicate with each other instantly. The application uses WebSocket technology for bidirectional communication between clients and the server, enabling real-time message exchange.

## Features

- Real-time messaging between multiple users
- Simple and intuitive user interface
- Instant message delivery using WebSocket
- Support for multiple concurrent users
- Message broadcasting to all connected clients

## Technologies Used

- **Backend**: 
  - Java 21
  - Spring Boot 3.5.7
  - Spring WebSocket
  - Spring Messaging (STOMP)
  - Thymeleaf (for templating)
  
- **Frontend**:
  - HTML5
  - Bootstrap 5
  - JavaScript
  - SockJS client
  - STOMP.js

- **Build Tool**: Maven

## Project Structure

```
ChatApp/
├── src/
│   ├── main/
│   │   ├── java/com/project/chatApp/
│   │   │   ├── Controller/
│   │   │   │   └── ChatController.java
│   │   │   ├── config/
│   │   │   │   └── WebSocketConfig.java
│   │   │   ├── model/
│   │   │   │   └── ChatMessage.java
│   │   │   └── ChatAppApplication.java
│   │   └── resources/
│   │       ├── templates/
│   │       │   └── chat.html
│   │       └── application.properties
│   └── test/
│       └── java/com/project/chatApp/
│           └── ChatAppApplicationTests.java
├── mvnw
├── mvnw.cmd
└── pom.xml
```

## Getting Started

### Prerequisites

- Java 21 or higher
- Maven 3.6 or higher
- IDE (IntelliJ IDEA, Eclipse, etc.)

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```

2. Navigate to the project directory:
   ```bash
   cd ChatApp
   ```

3. Build the project using Maven:
   ```bash
   ./mvnw clean install
   ```
   or on Windows:
   ```cmd
   mvnw.cmd clean install
   ```

### Running the Application

1. Run the application using Maven:
   ```bash
   ./mvnw spring-boot:run
   ```
   or on Windows:
   ```cmd
   mvnw.cmd spring-boot:run
   ```

2. Alternatively, you can run the JAR file:
   ```bash
   java -jar target/ChatApp-0.0.1-SNAPSHOT.jar
   ```

3. Open your browser and go to `http://localhost:8080/chat`

## Usage

1. Open your web browser and navigate to `http://localhost:8080/chat`
2. Enter your name in the "Your Name" field
3. Type your message in the message input field
4. Click "Send" or press Enter to send the message
5. The message will appear in the chat box for all connected users

## API Endpoints

- `GET /chat` - Displays the chat interface
- `POST /app/sendMessage` - Sends a message via WebSocket (mapped internally)

## WebSocket Configuration

The application uses STOMP over WebSocket for real-time communication:

- WebSocket endpoint: `/chat`
- Message mapping: `/app/sendMessage`
- Message broker: `/topic/messages`

The WebSocket is configured to allow connections from `http://localhost:8080`.

