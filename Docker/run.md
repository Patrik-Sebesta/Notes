- run docker 
````
docker run hello-world
````
bash - spustí bash


###parametre
"-t " - spustí ako terminal \
"-i " - spustí interaktívne \d 
"-d " - na pozadí  \
"-p" - zmena portu \
"-v" - namapovanie adresára \
"--name " - pomenovanie \ 

- adresár 
````
docker run -d --name redisMapped -v /opt/docker/data/redis:/data redis
````
- port 
````
docker run -d --name redisHostPort -p 6379:6379 redis:latest
````
- detaily o kontajneru 
````
docker logs <friendly-name|container-id>
````
- error logs
````
docker logs <friendly-name|container-id>
````
- zobrazí namapovanie portu 
````
docker port meno_instance  6379
```` 
