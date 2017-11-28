# ceos-docker

This project is to help in setting up a ceos container on docker. 

1. Docker-compose.yml: Contains the configurations required to setup the container

2. ceos.env: Contains the environment variables for the docker container

**Setup:**

1. Download and import the ceos image to docker:

```
wget  <url> -O cEOSLab.tar.gz
docker import cEOSLab.tar.gz ceosimage
```

2. Pull this repo to the local host

3. Edit the docker-compose.yml file and change the "image" variable to "ceosimage" or the name that you chose in the Step 1. 

4. Run "docker-compose":  

```
[Docker]$ docker-compose scale ceos=1  
WARNING: The scale command is deprecated. Use the up command with the --scale flag instead.  
Starting docker_web_1 ...  
Starting docker_web_1 ... done  
[Docker]$ docker ps -a  
CONTAINER ID        IMAGE               COMMAND             CREATED              STATUS              PORTS                    NAMES  
a4046e768ba1        ceosimage           "/sbin/init"        About a minute ago   Up 11 seconds                                docker_web_1  
```

If you want multiple ceos containers, increase the scale accoudingly. For example, to create 10 ceos containers, use "docker-compose scale ceos=10"
