docker-compose.yaml. is defalt name of compose file 
*advantages*
--> we many using the compse file for UP and DOWN the contaners for one commend
--> in the compose file we add versing the contaiers 
--> docker-compose file write in YAML formet

*exampile*

version: "3.9"
network:
  roboshop:
    driver: bridge
volume:
  mysql:
    driver: local
    driver_opts:
      type: none
      device: /home/full/path   # this the path where we connected the container
      o: bind   
services:
  web:
    image: web:v1 
    container_name: web
    depend_on:
    - mysql
    ports:
    - "80:80"    # this is we add port to the containers with on line 
  mysql:
    image: mysql.v1
    container_name: mysql
    volumes:
    -mysql:/var/lib/mysql  # this is path of data of mysql

--> in this exampile we add NETWROK & VOLUMES & PORTS & create NAMES of the containers & VERSION 
