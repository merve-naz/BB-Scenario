### CTF 2.Scenario

1. Create a folder for the project
```
mkdir Scenario
```
Clone the project repository from GitHub using Git:

```
cd Scenario
git clone https://github.com/merve-naz/BB-Senaryo-Dockerfile-Go.git
```

2. After clone,list the folder
```
ls
```
3. There will be a folder named "BB-Scenario-Dockerfile". This is the name of the project we pulled from github. Now let's go into this folder.

```
cd  BB-Senaryo-Dockerfile-Go
```

4. List the folder

```
ls 
```
We should see this output
 
- Dockerfile                  go.mod       main.go \  
- docker-compose.yaml         go.sum       public


5. We need to create a Docker image using the instructions and instructions in the Dockerfile, but the Dockerfile provided here is distrupted. We must review it first.

Open Dockerfile on vi editor
```
vi Dockerfile
```

6. After fixing the Dockerfile, we can now get docker build. Use the following command for this.
```
docker build -t my-bb-scenario-image .
```
7. Run Docker container: After creating a Docker image, enter the following command to run this image in a Docker container.
```
docker run -d --name my-container -p 8080:80  my-bb-scenario-image
```
8. Our application was successfully launched. To check this, you can use the "docker ps" command to see if the container containing our application is running and to which ports it is connected.

9. To replace the files in the image, you can enter a running Docker container using the docker exec -it command. Copy the following command.
```
docker exec -it   my-container /bin/sh 
```
10. Go the public folder
```
cd public
```
11. Let's change the index.html file in the public folder by opening it with the vi editor. For example, let's correct the "Hosgeldiniz BB" text as "WELCOME BB" and save it.
```
vi index.html```
Let's exit the container by typing ```exit``` 

12. Update your Docker image:
```
docker commit my-container myimage
```
Here, "myimage" is the name of your updated Docker image. Now your Docker image is updated by replacing the files in it.

13. To send this image we created to DockerHub, first create an account with "https://hub.docker.com/" by entering this site. If you have an account, create a new domain by saying create repository.

14. Enter the following command on the terminal screen. When the command runs, it will ask for the username and password you have registered.
``` 
docker login
```
15. If you want to upload a local image to a Docker hub repository, you must first identify that image with a tag.
```
docker tag <image_name> <docker_hub_username>/<repository_name>:<tag> 
```
We can find the version of the image by saying.```docker ımages``` 

16. Push the Docker image to Docker Hub:
```
docker push <docker_hub_username>/<repository_name>:<tag> 
```
