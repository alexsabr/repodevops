docker build -t alexandre/myapache2 .
docker run --network app-network --rm --name apache2-server -p 80:80 alexandre/myapache2

Q: Why do we need a reverse proxy ?
A: To be able to easily 
- load balance our various servers
- scale up or down easily depending on the needs
- hide the infrastructure behind a firewall or various networking rules

