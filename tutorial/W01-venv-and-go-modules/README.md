# Start Go Project

## Authors
- [Raden Alf Fajrus Shuluh](radenfajrus@gmail.com)

## Goals
Starting golang project using go modules  <br></br>

## Description
Golang is the hottest language nowadays.   
golang claimed to be the faster web service by maximizing utilization of concurent computation using message passing between cpu thread  
<br></br>

## Project setup instructions
To start using this project use the following commands:  

0. Install golang and vscode  
Go1.18.3 : https://go.dev/doc/install  
vscode : https://code.visualstudio.com/download  


1. Init Go Modules  
Go modules is needed to lock your dependecies  from development. For example, what happen if you have 2 folder that use same library with version. In nodejs or other language, there will be folder (node_modules/vendor/venv) to cache all library specific to the current project.  
\>> *Open Terminal in VSCode*  
`go mod init cqrs`  
This will create file go.mod (similar to package.json/Gemfile/composer.json)  

2. Install library  
`go get github.com/google/uuid`  
This will create file go.sum (similar to package-lock.json)   

3. Cache dependencies (Optional)  
`go mod vendor`  
This will create folder vendor contain copies of all package needed (similar to node_modules)  
This was optional because, if you compile go program. you will get binary with compiled package included. So, folder will not be used  

4. Activate Auto Complete on file.go  
\>> *Ctrl + Shift + P*  
\>> *Type: Go Install/Update Tools*  
\>> *Install All Package*  
\>> *Go to Extension*   
\>> *Install Extension "Go"*  

5. Test Run Program  
`go run main.go`  

6. Compile & Run  
`go build`  
`./cqrs.exe`  
`rm cqrs.exe`  

7. Compile & Run with Makefile  
`make build_and_run`  

8. Install Makefile using windows  
Many tutorial use Makefile to run go.  
However, its difficult to install `make` on Windows  
\>> *Open PowerShell*  
`Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))`
\>> *Download chocolatey windows: https://community.chocolatey.org/courses/installation/installing?method=installing-chocolatey#powershell*  
\>> *On PowerShell*  
`choco install make`



