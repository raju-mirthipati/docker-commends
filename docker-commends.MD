install docker in ec2-server 

docker commends 

--> docker pull <image-name>  [it will pull from image form docker hub]

--> docker create <image-id>  [it will create continer]

--> docker start <continer-id> [it will start the container]

--> docker stop <continer-id>  [it will stop the container] 

--> docker ps  [it will show all running containers]

--> docker ps -a  [it will show all running and deleted containers]

--> docker rm <container-id> [it will delete the container]    
    
--> docker rmi <image-id> [it will delete the image] 

--> docker run <image-name>  [it will pull image from docker hub and create container]  
                                        { docker run = pull + create + start }
 
--> docker run -d -p <port:port> <image-name> [it will attach the internal port to container]   
 
--> docker run -d -p <container-port:host-port> --name <coustom-name> <image-name> [ it will attach the name to container]

--> docker exec -it <conatiner-id> bash  [ it will get into the conatiner]

--> docker logs <container-name> [ it will shows the logs of the container ]

--> docker 




when we want to build our own image then create one Dockerfile 
docker has separete syntex to create Dockerfile
- inside the Dockerfile we write like this 

FROM ubuntu --> [this is refence of ubuntu image as in dockerhub]

to build the image what we write in Dockerfile
if you want to build your coustom image the path shoud be from dockerfile

--> docker build -t <dockerhub-url>/<user-name>/<coustom-name>:<version> .

to push the image form local to dockerhub

--> docker push <user-name>/<coustom-name>:<version>
                             
                        

--DOCKER VOLUMES--

-> docker containers are ephemeral

-> when we want to create docker image and next we create docker container the container use's the host files system to as a volume 

-> when we want to delete the conatiner all data was deleted 

DOCKER VILUMES ARE TWO TYPES 

1. Named volumes 
2. Unamed volumes

Named volumes. mainted by docker 
Unamed volumes. not mainted by docker



 if we mount the docker volume to the container the data was unbroken 

*formet to attch the docker volume to container*

-> docker volume create <volume-name>

-> docker volume ls [to see the all docker volumes]

-> docker run -d -v <volume-name>:</path/of/mouted/to/the/container> -p <docker-port>:<host-port> <image-name>:<version>


DOCKER NETWORK 
-
when we want to containers to communicate each other we want to create and attch the networks to the containers in the docker we have 4 types of netwroks is there

1. brige network
2. overlay networks
3. multi-host communication
4. macvlan networks

we are commenly use the brige network's becase of bridge netwrok communicate with the container names
 *formet to attch the docker volume to netwroks*

 --> docker create netwrok <name>
 after ceate the netwrok we add the netwrok for the conatiners in this formet
 --> docker run -d --netwrok <netwrok name> --name <name> <image-name>:<version>


