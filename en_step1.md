### CTF 2.Scenario

1. Pull the project from the relevant address.
```
https://github.com/merve-naz/BB-Senaryo-Dockerfile-Go.git
```
2. After pulling the project into our scenario folder, you can list it and see its contents.

3. There will be a folder named "BB-Senaryo-Dockerfile-Go" here. This is the name of the project we pulled from GitHub. Now, go into this folder.

If you see this output, you can proceed:
- Dockerfile go.mod main.go
- docker-compose.yaml go.sum public

4. We need to create a Docker image using the instructions and guidelines in the Dockerfile, but there are missing parts in the provided Dockerfile. First, we need to fix this.

5. Let's open the Dockerfile in a text editor to do this.

6. After fixing the Dockerfile, we can now build the Docker image. (You can give a tag when creating a Docker image. Use the "latest" tag for this scenario.)

7. Run the Docker container.

8. After our application successfully starts, review whether the container is running and which ports it is connected to.

9. You can enter a running Docker container to modify the files inside the image using the relevant command.

10. Review the files and folders, then go to the public folder.

11. Open the index.html file in the public folder with a text editor and make the following change: Correct "Hoşgeldiniz BB" to "WELCOME TO BB".

- Exit the container.
12. Stop the Docker container and start it up again with the newly created image.

13. To upload this image to DockerHub, first create a profile on the DockerHub website.

14. Enter the following command in the terminal. When the command runs, it will ask for your username and password for the account you signed up for:
```
docker login
``` 
15. To upload your Docker image to Docker Hub, you first need to tag your image with your Docker Hub username. (If you did this when creating the image in step 6, you don't need to do it again.)

16. Push the Docker image to Docker Hub.
