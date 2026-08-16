# QuestFlow
QuestFlow is a workflow and project management platform built with Java and Spring Boot.  The project is designed both as a production-style application and as a portfolio project demonstrating backend development, software architecture, automated testing, databases, security, Docker and professional Git workflows.

Project Goals

QuestFlow allows teams to create projects, tasks and customizable workflows.

A workflow can define states such as:

Pending
   ↓
In Development
   ↓
Code Review
   ↓
Testing
   ↓
Completed

Transitions between states can contain business rules that determine whether a task is allowed to move to the next state.

🛠 Technology Stack
Backend
Java 21
Spring Boot
Spring Web
Spring Data JPA
Hibernate
Spring Security
Bean Validation
Database
PostgreSQL
Flyway
Testing
JUnit 5
Mockito
Testcontainers
Infrastructure
Docker
Docker Compose
API Documentation
OpenAPI
Swagger UI
Build
Maven
Maven Wrapper
CI/CD
GitHub Actions

Architecture

QuestFlow follows a layered architecture with clear separation of responsibilities.

Controller
    ↓
Application / Service
    ↓
Domain
    ↓
Repository
    ↓
PostgreSQL

Initial package structure:

com.yatagarasu.questflow

├── config
├── auth
├── user
├── project
├── workflow
├── task
└── shared

The architecture may evolve toward Hexagonal / Clean Architecture when the complexity of the application justifies it.

Main Modules

QuestFlow will initially contain the following modules:

Authentication
Users
Projects
Project Members
Workflows
Workflow States
Workflow Transitions
Tasks
Comments
Audit History

Git Workflow

Development must not be performed directly on main.

Every change starts from a GitHub Issue.

GitHub Issue
     ↓
Branch
     ↓
Development
     ↓
Tests
     ↓
Pull Request
     ↓
Code Review
     ↓
Merge into main
Branch naming
feat/<issue>-description
fix/<issue>-description
refactor/<issue>-description
test/<issue>-description
docs/<issue>-description
chore/<issue>-description

Examples:

feat/1-bootstrap-backend
feat/8-user-registration
fix/26-duplicate-project-members
refactor/31-workflow-service
test/35-workflow-transition-rules
docs/40-update-api-documentation

Issues

Every significant change should have an associated GitHub Issue.

An Issue should ideally include:

Title
Description
Requirements
Acceptance Criteria
Technical Notes (when necessary)

Example:

#8 Implement user registration

Requirements:

- POST /api/auth/register
- Validate email
- Validate password
- Prevent duplicate emails
- Hash passwords
- Persist the user

Acceptance Criteria:

- A valid user can register
- Duplicate emails are rejected
- Invalid requests return HTTP 400
- Passwords are never stored as plain text
- Automated tests are included

  AI / Codex Development Policy

Codex may be used as an implementation assistant during development.

However:

No significant code should be merged into QuestFlow unless we understand what the code does and why it was implemented that way.

The expected workflow is:

Define requirement
        ↓
Create GitHub Issue
        ↓
Design solution
        ↓
Codex implementation
        ↓
Human review
        ↓
Understand the implementation
        ↓
Run tests
        ↓
Pull Request
        ↓
Merge

AI-generated code must be treated exactly like code written by another developer and must therefore be reviewed before being accepted.

Testing Philosophy

Business logic should be covered by automated tests.

QuestFlow will use:

Unit Tests
Integration Tests
Repository Tests
API Tests

Critical workflow rules should always have automated tests.

Local Development

The application will use Docker Compose to provide infrastructure services such as PostgreSQL.

Expected development environment:

Java 21
Git
Docker Desktop
IntelliJ IDEA

PostgreSQL does not need to be installed directly on the host machine.

The application will eventually be started with commands similar to:

docker compose up -d
./mvnw spring-boot:run

Windows:

docker compose up -d
.\mvnw.cmd spring-boot:run

Development Roadmap
Phase 0
Project Foundation

        ↓

Phase 1
Users & Authentication

        ↓

Phase 2
Projects & Members

        ↓

Phase 3
Workflow Definition

        ↓

Phase 4
Tasks

        ↓

Phase 5
Workflow Engine

        ↓

Phase 6
Audit & History

        ↓

Phase 7
Testing & Hardening

        ↓

Phase 8
Deployment & Portfolio Release

Development Principles

QuestFlow should prioritize:

Clear code over clever code.
Business logic outside controllers.
Small and focused classes.
Explicit domain rules.
Automated tests for critical behavior.
Database migrations instead of manual schema changes.
Secure defaults.
Meaningful commits.
Traceability between Issues, branches and Pull Requests.
Documentation of important architectural decisions.

Portfolio Objective

QuestFlow should demonstrate the ability to build and maintain a professional backend application using the Java ecosystem.

The final project should demonstrate knowledge of:

Java
Spring Boot
REST APIs
Authentication
Authorization
Relational Databases
JPA / Hibernate
Database Migrations
Docker
Testing
Software Architecture
Git
GitHub
CI/CD
