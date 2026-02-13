# Build Log — Caseflow CRM

This document records **every command, test, and verification step** performed during development.
Newest steps go at the top.

---

## Step 0: Project Scaffold + Local API Smoke Test

### Goal
Set up a clean repo structure and confirm the .NET Web API can run locally and respond to an HTTP request.

### Commands executed (in order)

#### System prep (WSL)
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y curl unzip 
```
- `apt update` refreshes the package list 
- `apt upgrade` updates installed packages (had to switch update to WSL2 then turn on SVM whatever in BIOS)
- `curl` = command-line tool to make HTTP requests (used to test our API)
#### Install .NET SDK 
```bash
sudo apt install -y dotnet-sdk-8.0
dotnet --version
```
- *.NET SDK* includes the C# compiler, the `dotnet` CLI, and templates liek `webapi`
- `dotnet --version` to check if the toll is installed and callable from shell 
#### Create repo folder structure 
```bash 
cd 
mkdir caseflow-crm
cd caseflow-crm

mkdir backend frontend docs
```
- `backend/` will contain the server side API (C#/.NET)
- `frontend/` will contian the browser UI (HTML/CSS/JS) later
- `docs/` will contain documentation (like this file, i'm so origanized)
#### Create a .NET Web API project 
```bash
cd backend 
dotnet new webapi -n Caseflow.Api
cd Caseflow.Api
```
- `dotnet new webapi` generates a starter REST API project with default files 
- `-n Caseflow.Api` names the project and creates a folder, `Caseflow.Api/`
- the result is a runnable web server project 
#### Run the API server locally 
```bash
dotnet run 
```
- build the project (compiles C#)
- starts a local web server that keeps running until you stop it (Ctrl + C)
- The terminal prints URLs like:
    - Now listening on: https//localhost:<PORT>
#### Tests performed 
*testing the example endpoint:*
- open a second terminal while `dotnet run` is still running in the first 
- using the exact port printed by `dotnet run` in the first terminal, run HTTP test:
```bash
curl http://localhost:<HTTP_PORT>/weatherforecast
```
- JSON should print to the terminal 
- this test confirms the api server is reachable, routing works, and the environment is set up correctly 