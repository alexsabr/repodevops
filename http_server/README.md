command to build the image
docker build -t alexandre/myapache2 .

command to run the container
docker run --network app-network --rm --name apache2-server -p 80:80 alexandre/myapache2


