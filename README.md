# erocci-docker
*erocci*'s Dockerfile and resources will run a local erocci on port.

### Install required software
* Install Docker (http://docs.docker.com/linux/step_one/). 
  1. Run the next command as root: ```$ wget -qO- https://get.docker.com/ | sh ```
  2. Then verify if its installed an can run using command: ```$ docker run hello-world ```


## Usage - Load docker image
* As described in : https://hub.docker.com/r/erocci/erocci/ (if it ask for permitions, "Cancel" the pop-up and it will show the image details).

  1. Download the image: `$ sudo docker pull erocci/erocci`
  2. Load image to the container: `$ sudo docker run --name demo_erocci -p 80 -d erocci/erocci`

* To check the current images, run command: `$ sudo docker images`

* To check on which port from outside of the container is erocci accessible :  `$ sudo docker ps`

  Then you will see something like :
  ```
  CONTAINER ID  |IMAGE          |COMMAND         |CREATED         |STATUS        |PORTS                  |NAMES
  XXXXXXXXXXXX  |erocci/erocci  |"/root/run.sh"  |X minutes ago   |Up X minutes  |0.0.0.0:XXXX->80/tcp   |demo_erocci
  ```
  As you can see, *erocci* is running on port 80 in the container. 

* Query *erocci* with curl, for instance: 
  `$ curl -v -H 'accept: application/json' http://localhost:XXXXX/-/`

## Customization

* Would you just need to change the exposed OCCI schema, map an OCCI XML schema to `/tmp/occi.xml`

* Would you need to change global erocci configuration, map your *erocci* config file to `/tmp/sys.config`
  
