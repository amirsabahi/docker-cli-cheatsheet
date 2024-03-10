# docker-cli-cheatsheet

docker info 'Display system information'

docker version 'Displayes the system version'

docker login 'Login to a docker registery' 

docker pull [imageName] 'Pull an image form registery'

docker run [imageName] 'Run containers'

docker run --name [name] --publish [port:port] [imageName] 'Run containers'

docker run -d [imageName] 'Run the container in the background or detached mode'

docker run -it [imageName] -- /nib/shell 'Attach Shell'

docker run -it [imageName] -- microsoft/powershell:nanoserverpwsh.exe 'Attach power shell

docker container exec -it [containerName] -- bash 'Attach to a running container'

docker start [containerName] 'Start stopped container'

docker ps 'List running container'

docker ps 'List running and stopped containers'

docker stop [containerName] 'Stop container and keep the conatainer in memory'

docker kill [containerName] 'Kills container'

docker image inspect [imageName] 'Display infors about an image'

### Clean up
docker rm [containerName] 'Remove from memory after stopping'