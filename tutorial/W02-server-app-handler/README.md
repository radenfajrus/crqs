# Start Go Project

## Authors
- [Raden Alf Fajrus Shuluh](radenfajrus@gmail.com)

## Goals
Web Framework and Running Server
<br></br>

## Description
Currently, fasthttp become more popular golang web framework on par with gin or go-chi. Some people said that it give better performance. But, its a bit complicated to code.  
For those who come from another language, such as python or nodejs, its recommended to use gofiber.  
Go Fiber is a web framework library wrapped from fasthttp. It has friendlier syntax and flow similar to nodejs. From company pov, its easier to maintain.   
<br></br>

## Project setup instructions
To start using this project use the following commands:  

1. Install Go Fiber v2 
`github.com/gofiber/fiber/v2`  

2. Edit main.go 

        package main  
        import "github.com/gofiber/fiber/v2"  
        func main() {
            app := fiber.New()
            app.Get("/", func(c *fiber.Ctx) error {
                return c.SendString("Hello, World 👋!")
            })
            app.Listen(":3000")
        }


3. Run hot loaded with Air  
Air library is the easiest way to run hot reloaded server.  
`go install github.com/cosmtrek/air@latest`  
Start > Search > edit the system environment variable.  
Check apakah path sudah mengarah ke %USERPROFILE%\go\bin  dan di folder tersebut ada file air.exe  
`air`  
Open http://127.0.0.1:3000/

4. Setup Folder  
Root Folder Structure  
    - deploy : for deployment / cicd purpose 
    - log    : folder log, harus 1 folder dgn script run 
    - public     : Frontend / Static File Server
    - script : script bash/3rdparty/migration/etc  
    - src    : Backend  
      - abstract    : contract / abstract class that important. being named abstract to make sure it sorted at the top (letter ab).
      - api    : routes
        - v1.go    : routes for v1
        - v2.go    : routes for v2
      - app    : core program
        - api : Wrapper service to 3rd party api
          - api1.com   
          - api2.com   
        - auth :
          - handler.go  : controller in other language, handle in golang 
          - dto.go
          - model.go
          - service.go
          - repo.go
        - home :
          - handler.go 
          - dto.go
          - model.go
          - service.go
          - repo.go
          - util.go
        - event : 
          - handler.go
          - event1.go
          - event2.go
          - event3.go
        - error : 
          - handler.go
          - error1.go
          - error2.go
          - error3.go
      - config    : Config model that accepted from .env
      - data    : Dummy data, to speedup frontend development, before database ready.
      - infra    : connection to other infra (db,mq,memcache,api,file)  
        - db   
          - model
          - client.go
          - config.go
        - mongo  
          - model
          - client.go
          - config.go
        - redis  
          - client.go
          - config.go
        - mqtt  
          - client.go
          - config.go
        - file  
          - storage
          - client.go
          - config.go
        - api  
          - api1.go
          - api2.go
        - manager.go : Repo Manager
        - circuit_breaker.go : HealthChecking each infra connection status  
      - util    : global function / helper 
      - main.go    : script run server http 
      - ws.go      : script run server ws  
      - grpc.go    : script run server grpc
      - worker.go    : script run worker background
      - logger.go    : custom logger function
      - middleware.go    : custom middleware function
      - .env : environment variable
    - Makefile : Script to run app  
    - REAME.md : notes     
  
  
  
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



