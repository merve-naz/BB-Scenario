### Step 4: Create a Dockerfile
Now that we have our code, we need to create a Dockerfile that will allow us to build a Docker image for our microservice.

Create a new file named Dockerfile in the root directory of your project.

Open the Dockerfile in your text editor and add the following contents:

```
FROM golang:alpine

WORKDIR /app

COPY go.mod .
COPY go.sum .
RUN go mod download

COPY . .

RUN go build -o main .

EXPOSE 8080

CMD ["./main"]
```
This Dockerfile uses the official golang:alpine image as its base. It sets the working directory to /app, copies the go.mod and go.sum files, and runs go mod download to download the dependencies.

Then it copies the rest of the project files and runs go build to build the binary. The EXPOSE instruction tells Docker that the container will listen on port 8080, and the CMD instruction specifies the command to run when the container starts.

Save and close the Dockerfile.