docker build -t alexandre/mypostgres .
docker network create app-network
docker run -d -p 15432:5432 --rm  \
--name=webpsql -v /home/alexandre/Desktop/DEVOPS/c1/TP/mydatadir:/var/lib/postgresql/data \
--env=POSTGRES_PASSWORD=pwd \
--network app-network  alexandre/mypostgres


Tip Question: Why do we need a volume to be attached to our postgres container?
Answer : So we keep the databases data even after the container has been removed

adminer config : put container name in localhost 

/docker-entrypoint-initdb.d
