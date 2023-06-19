# simple-api-devops

command to build the image : 
docker build --tag alexandre/mybackend .

command to run the container
docker run  --rm --network app-network -p 8080:8080  --name small_backend alexandre/mybackend
