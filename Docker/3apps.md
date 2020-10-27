- run nginx, mysql a httpd
- porty    
    - nginx 80:80 
    - httpd 8080:80
    - mysql 3306:3306  
- mysql  -e MYSQL_RANDOM_ROOT_PASSWORD=yes
````
docker run  -d -p 3306:3306 --name db --e MYSQL_RANDOM_ROOT_PASSWORD=yes mysql 
docker run -d -p 8080:80 --name webserver -p 8080:80 httpd 
docker container run --name proxy -d -p 80:80 nginx
````
iuPaikooN3ainge2Ohpahsooma9Ou1ah

- test 
````
curl localhost
curl localhost:8080
````
