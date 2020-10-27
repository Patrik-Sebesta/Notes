



- Client a deamon su na jednom hoste 
- client server model 
- client vola demona pri do  cker run

#### Swarm
A claster = A swarm \
 
  ***Manager nodes*** - managuje swarm
  odporúčane 3 až 5 - jeden z nich je ***leader***.
  
  ***Worker node***  - spúšťa ***services***.
  
````
docker service create --name web-fe --replicas 5 ... 
````
***Tasks*** - priradene workerom 
*** Services *** - Declarative

### príklad 
- 6  nodov - 3x manager a 3x worker
````
docker swarm init --advertise-addr 172.31.12.161:2377 --listen-addr 172.31.12.161:2377
```` 

````
docker swarm join-token manager 
````
- vypluje to token, ktorý treba pridať do  workera alebo managera. 

- promote worker to manager  
````
docker poromote ID
````


### Services
Stavy - desired a Actual 

````
docker service create --name psight1 -p 8080:8080 - replicas 5 image_meno
````
- info o bežiacej service 
 ````
docker meno_service inspect
````

- nastavenie kolko nodov má bežať. 
````
docker service scale meno_service=7
````

### Stack and Bundles
