# docker-cli-cheatsheet

docker info `Display system information`

docker version `Displays the system version`

docker login `Login to a docker registry` 

docker pull [imageName] `Pull an image form registry`

docker run [imageName] `Run containers`

docker run --name [name] --publish [port:port] [imageName] `Run containers`

docker run -d [imageName] `Run the container in the background or detached mode`

docker run -it [imageName] -- /nib/shell `Attach Shell`

docker run -it [imageName] -- microsoft/powershell:nanoserverpwsh.exe `Attach power shell

docker container exec -it [containerName] -- bash `Attach to a running container`

docker start [containerName] `Start stopped container`

docker ps `List running container`

docker ps `List running and stopped containers`

docker stop [containerName] `Stop container and keep the container in memory`

docker kill [containerName] `Kills container`

docker image inspect [imageName] `Display information about an image`

docker images `list images`

docker ps --filter status=exited --filter status=dead -q `Which containers are unused?`

### Clean up
docker rm [containerName] `Remove from memory after stopping`

docker rm (docker ps -a -q) `Remove all stopped containers`

docker rmi [imageName] `Delete the given image`

docker system prune -a `CAUTION -> Remove all unused images not just dangling ones` 

docker system prune -f `CAUTION -> Remove everything` 

docker image prune -f `Remove all images not used by containers `

docker buildx prune -f `Remove build-cache`

### Building Containers

docker build -t [name:tag] `Builds an image using the docker file located at the same directory`

docker build -t [name:tag] -f [fileName] `Builds an image using the docker file located at a different directory`

docker tag [imageName] [nameTag] `Tag an existing image`

### Volume

docker create volume [volumeName] `create a new volume`

docker volume ls `List the volumes`

docker volume inspect [volumeName] `Display the volume info`

docker volume rm [volumeName] `Deletes a volume`

docker volume prune `CAUTION: Delete all volumes not mounted`

docker run -d --name devserver -v myvol:/app nginx:latest `Run a command with volume`

### Docker Compose

docker compose build `Build the images. Use -f to specify the file location`

docker compose start `Start the containers`

docker compose stop `Stop the containers but they remain in memory`

docker compose up -d `Build and start. Use -d to run in background`

docker compose ps `List what's running`

docker compose rm `Remove containers from memory`

docker compose down `Stop and remove`

docker compose logs `Get the logs`

docker compose exec [container] bash `Run a command in a container`

docker compose --project-name [name] up -d `Run an instance as a project`

docker compose -p [projectName] up -d `Shortcut for the command above`

docker compose ls `List running projects`

docker compose cp [containerID]:[SRC_PATH] [DEST_PATH] `Copy files from containers`

docker compose cp [SRC_PATH] [containerID]:[DEST_PATH] `Copy firls to the container`

### Publish to docker hub

docker login -u <username> -p <password> `Login to dockerhub`

docker tag my_image orginization_name/my_image:latest `Tag the image previously built`

docker push orginization_name/my_image:latest `Push the image`

docker pull orginization_name/my_image:latest `Pull the image`
