# canvas
A blank canvas for your web app, in Go.

This repository is used in the course [Build Cloud Apps in Go](https://www.golang.dk/courses/build-cloud-apps-in-go).

## Project structure
Everyone has different preferences for project structure, and there is no right way to do it. That said, in canvas we follow some conventions that work quite well:

Config files, the go.mod/go.sum files, the Makefile, and more, are in the root folder.
The cmd/server/ directory has the main package and function that starts the server.
The server/ directory will hold the HTTP server setup and running code.
The handlers/ directory will have all the HTTP handlers.
The Makefile is a convenience so that we have to type less. It uses the go command for testing, coverage, and starting the server.

Try running make start, and you should see a nerdy smiley on your terminal:

```
$ make start
go run cmd/server/*.go
🤓
```
To run your tests and see coverage, run make test cover:

```
$ make test cover
go test -coverprofile=cover.out -short ./...
?   	canvas/cmd/server	[no test files]
?   	canvas/handlers	[no test files]
ok  	canvas/server	0.286s	coverage: [no statements] [no tests to run]
go tool cover -html=cover.out
```