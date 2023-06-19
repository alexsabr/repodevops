command to build the image :
docker build -t alexandre/mypostgres .

command to create a network
docker network create app-network


command ot run the image in a container 
 !! CHANGE THE BINDING PATH ON HOST IF YOU ARE  ON ANOTHER MACHINE !!

docker run -d -p 15432:5432 --rm  \
--name=webpsql -v /home/alexandre/Desktop/DEVOPS/c1/TP/mydatadir:/var/lib/postgresql/data \
--env=POSTGRES_PASSWORD=pwd \
--network app-network  alexandre/mypostgres



adminer config : put container name in localhost 

/docker-entrypoint-initdb.d
