# simple-api-devops
docker build --tag alexandre/mybackend .
docker run  --rm --network app-network -p 8080:8080  --name small_backend alexandre/mybackend
