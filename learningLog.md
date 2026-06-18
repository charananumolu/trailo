# Trailo Learning Log

## Phase 0 - Day 1

### Goal

Set up the Trailo development environment and establish the project foundation before starting feature development.

---

## Learn

### Git & Repository Setup

* Initialized a Git repository for Trailo.
* Understood the purpose of version control and source code management.
* Learned the difference between local and remote repositories.

### Spring Boot Setup

* Generated a Spring Boot project using Spring Initializr.
* Added foundational dependencies:

  * Spring Web
  * Spring Security
  * Spring Data JPA
  * PostgreSQL Driver
  * Validation
  * Lombok
  * Actuator

### React Setup

* Generated a React application using Vite.
* Understood why Vite is preferred over Create React App for modern React development.

### Environment Configuration

* Learned the importance of JAVA_HOME.
* Learned how Maven Wrapper (mvnw) works.
* Learned how PowerShell execution policies can affect npm commands.

---

## Understand

### Why We Start With a Monolith

Trailo roadmap follows:

Monolith → Microservices → Cloud

Building microservices from Day 1 would introduce unnecessary complexity and reduce learning effectiveness.

### Why Git Ignore Matters

Only source code and project configuration should be committed.

Generated artifacts such as:

* target/
* node_modules/
* IDE metadata

should not be stored in Git.

### Why Spring Boot Failed Initially

Spring Boot detected:

* Spring Data JPA
* PostgreSQL Driver

and automatically attempted to create a datasource.

Since no database configuration was provided, startup failed.

---

## Apply

### Project Structure Created

trailo/
├── backend/
├── frontend/
├── docs/
│   ├── architecture/
│   ├── lld/
│   └── decisions/
├── README.md
├── LEARNING_LOG.md
└── .gitignore

### Backend

* Spring Boot project successfully created.
* Application started successfully on port 8080.

### Frontend

* React + Vite project successfully created.
* Application started successfully on port 5173.

### Git

* Repository initialized.
* Initial commit created.
* GitHub repository connected.

---

## Implement

### Running Applications

Backend:
mvnw.cmd spring-boot:run

Frontend:
npm run dev

Successfully verified:

* Backend running on localhost:8080
* Frontend running on localhost:5173

---

## Issues Faced & Resolution

### Issue 1: JAVA_HOME Not Configured

Error:

The JAVA_HOME environment variable is not defined correctly.

Root Cause:

* Java was installed but JAVA_HOME was not configured.

Resolution:

* Configured JAVA_HOME system variable.
* Added %JAVA_HOME%\bin to PATH.
* Restarted terminal.

Outcome:

* Maven Wrapper executed successfully.

---

### Issue 2: Spring Boot Datasource Configuration Failure

Error:

Failed to configure a DataSource

Root Cause:

* Spring Boot detected JPA dependencies and attempted database configuration.
* PostgreSQL settings were not yet configured.

Resolution:

* Temporarily disabled datasource auto-configuration:

spring.autoconfigure.exclude=org.springframework.boot.autoconfigure.jdbc.DataSourceAutoConfiguration

Outcome:

* Application started successfully.

---

### Issue 3: PowerShell Blocked npm Commands

Error:

npm.ps1 cannot be loaded because running scripts is disabled on this system.

Root Cause:

* PowerShell execution policy blocked npm script execution.

Resolution:

* Switched to Command Prompt.
* Identified PowerShell execution policy restrictions.

Outcome:

* React application generated successfully.

---

### Issue 4: GitHub Push Failed

Error:

non-fast-forward
refusing to merge unrelated histories

Root Cause:

* Local repository and GitHub repository had separate histories.

Resolution:

* Connected remote repository correctly.
* Force pushed once to establish local repository as source of truth.

Outcome:

* GitHub repository synchronized successfully.

---

## Decisions Made

### Technology Decisions

Current Setup:

* Java 17 (temporary)
* Spring Boot 3
* PostgreSQL 16
* React + Vite
* GitHub

Planned Upgrade:

* Upgrade Java 17 → Java 21 before Phase 1.

### Architecture Decisions

Follow roadmap strictly:

Phase 1:

* Monolith

Phase 4:

* Microservices
* Kafka

Phase 5:

* Docker
* AWS

No premature introduction of:

* Kafka
* Redis
* Docker
* Kubernetes
* AWS

---

## Key Takeaways

* Environment setup issues are normal and part of engineering.
* Reading error messages carefully often reveals the root cause.
* Modern projects require understanding both backend and frontend tooling.
* Proper repository setup and commit hygiene are important from Day 1.
* Trailo development environment is now fully operational.

---

## Day 1 Outcome

Status: COMPLETED ✅

Backend Running: ✅
Frontend Running: ✅
Git Repository Initialized: ✅
GitHub Connected: ✅

Ready for:
Phase 0 - Day 2
Git Workflow, Branching Strategy, Commit Standards, and Debugging Fundamentals.
