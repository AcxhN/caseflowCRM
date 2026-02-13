# caseflowCRM readme Post Step 0: Project Scaffold + Local API Smoke Test

## Overview
Caseflow CRM is a mini “Dynamics-style” business application for managing:
- Clients
- Cases (tickets)
- Activity logs (audit trail of changes)

The goal is to practice building a real-world CRUD + workflow system using a Microsoft-aligned stack.

## Learning Objectives
By building this project, I will be able to:
- Build REST APIs in C# using ASP.NET Core (.NET)
- Model data and relationships for business apps (SQL Server + EF Core)
- Implement business rules (status transitions, validation, audit logging)
- Integrate a frontend UI with an API using JavaScript `fetch`
- Use Git professionally (small commits, meaningful messages, clean repo history)
- Document setup and development steps clearly for interviews

## Tech stack
**Backend**
- C# / .NET 8 — ASP.NET Core Web API
- Swagger/OpenAPI (built-in) for API exploration

**Frontend (planned)**
- HTML, CSS, JavaScript (Fetch API)
- Optional later: React

**Database (planned)**
- likely a SQLite3 Server
- Entity Framework Core (EF Core)

**Dev Tools**
- Git + GitHub
- WSL version: 2.6.3.0 (Ubuntu)     
- Kernel version: 6.6.87.2-1    

## Project Structure
ran cmd: `tree -I "bin|obj|*.json` printed tree at root of project ignoring bin and obj folders and all json files
```
.
├── README.md
├── backend
│   └── Caseflow.Api
│       ├── Caseflow.Api.csproj
│       ├── Caseflow.Api.http
│       ├── Program.cs
│       └── Properties
├── docs
│   └── build_log.md
└── frontend
```
- `/backend` C#/.NET Web API (server)
    - `Caseflow.Api.csproj` project configuration file
    - `Program.cs` this is the entry point (it configures the web server, sets up routing, registers services and starts the app)
- `/frontend` Static web UI (HTML/CSS/JS) 
- `/docs` Build log + architecture + API + database notes

#### Run the backend API locally
```bash
cd backend/Caseflow.Api
dotnet run
```
Then use the printed http://localhost:<PORT> URL to test:
`curl http://localhost:<PORT>/weatherforecast`
