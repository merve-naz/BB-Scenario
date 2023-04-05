### Step 5: Build the Docker image
Now that we have our Dockerfile, we can build a Docker image for our microservice.

Open a terminal and navigate to the root directory of your project.

Run the following command to build the Docker image:

```
docker build -t my-go-microservice .
```
This command builds a Docker image with the tag my-go-microservice. The . at the end tells Docker to use the current directory as the build context.

Wait for the build to complete. This may take a few minutes, depending on your internet connection and the size of your project.

Step 6: Run the Docker container
Now that we have a Docker image, we can run a Docker container from that image.

Run the following command to start a Docker container:

```
docker run -p 8080:8080 my-go-microservice
```
This command starts a new Docker container from the my-go-microservice image and maps port 8080 in the container to port 8080 on your local machine.

Open your web browser and navigate to http://localhost:8080/. You should see a message that says "Hello, World!".

Congratulations! You have successfully created a microservice with Go and deployed it to a Docker container. In the next step, we will learn how to deploy this container to a cloud platform.