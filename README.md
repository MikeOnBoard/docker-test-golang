# **Docker test with golang**
## **Project Structure**
```go
docker-test-golang/
├── Dockerfile
├── main.go
├── README.md
```
## **Overview**
docker-test-golang is a basic project designed to demonstrate the deployment of a Golang application within a Docker container. It serves as a template for testing and understanding Dockerized environments for Go applications, providing a functional structure for Go projects with Docker.

## **Prerequisites**
Ensure you have the following installed:

- **Go**: Go installation
- **Docker**: Docker installation
## **File Descriptions**
- **Dockerfile**: Defines the instructions to build and run the Go application within a Docker container.
- **main.go**: Contains the main application code.
- **go.mod** / **go.sum**: Dependency files for Go modules, used to manage package dependencies.
## **Installation and Setup**
1.**Clone the Repository**

```bash
git clone https://github.com/MikeOnBoard/docker-test-golang.git
cd docker-test-golang
```
2.Build the Docker Image Build the image using Docker from the project root directory:

```sh
docker build -t docker-test-golang .
```
3.Run the Docker Container Run the container using the image built in the previous step:

```sh
docker run -it docker-test-golang
```
## Code Overview
### **main.go**
```go
package main

import (
    "fmt"
)

func main() {
    fmt.Println("Hello, Dockerized Golang!")
}
```
This application is a simple Go program that outputs a message confirming that the Go environment is running within Docker.

### **Dockerfile**
```dockerfile
# Start from the official Golang image
FROM golang:1.16

# Set the working directory
WORKDIR /app

# Copy the source code into the container
COPY . .

# Build the Go application
RUN go build -o main .

# Set the default command to run the executable
CMD ["/app/main"]
```
This ``Dockerfile`` initiates the application by:

1.Starting from the official Go base image.
2.Copying project files into the container.
3.Compiling the application.
4.Running the executable.
## **Usage**
- Build and Run in One Step: To build and start the container in one go, use:

```sh
docker-compose up --build
```
- Stopping the Container:

```sh
docker stop <container_id>
```
- Viewing Logs:

```sh
docker logs <container_id>
```
## **Conclusion**
The docker-test-golang project serves as a streamlined, modular approach to deploying a Go application in a Docker environment. This setup can be used as a foundation for building more complex Dockerized applications with Go, facilitating portability, ease of deployment, and scaling in containerized environments.