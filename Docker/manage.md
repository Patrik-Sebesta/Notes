###Manage 


- všetky kontainery
````
docker ps -a 
````
- docker images uložene lokalne 
````
docker images 
````
- stiahnutie image 
````
docker pull meno_image:verzia"
````
pri nezadani verzie sa stiahne latest

-  zmazanie image
```` 
docker rmi meno_image
````

###Container lifecycle 
minimalizovať kontainer 
````
ctrl + p + q 
````
- stop all kontainers 
````
docker stop $(docker ps -aq)
````
-----------------------------------------
#nove videa

````
docker container run --publish 80:80 nginx
````
- stiahne image 'nginx' z dockerHubu
- naštartuje nový kontajner z tohoto image
- otvorí port 80 na host IP 
- presmeruje traffic na kontainer, na port 80 


### logy
````
docker container logs (meno alebo container ID) 
````

### info o kontajnery 
````
docker container top  ID 
````
````
docker inspect [meno]
````
### zmazanie 
````
docker container rm -f ID 
````


