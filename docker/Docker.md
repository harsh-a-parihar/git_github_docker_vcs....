# Docker
---------
### Docker is used to automate the software deve1opment process. It is a tool designed to make it easier to create, deploy, and run applications by using containers. Containers allow a developer to package up an application with all of the parts it needs, such as libraries and other dependencies, and ship it all out as one package.


## Installation

1. Manually: Go through the below link to download.

    ```
    https://www.docker.com/products/docker-desktop/
    ```
2. Using terminal:

    ```
    sudo apt update -y
    sudo apt install docker.io -y
    ```
3. To verify the installation:

    ```
    sudo docker info
    ```

## Functions and Use Cases

1. Start docker service:

    ```
    sudo systemctl start docker
    ```


2. Start docker service when the system bootsup:

    ```
    sudo systemctl enable docker
    ```


3. To list all running containers:

    ```
    docker ps
    ```

    To list all containers (runing & stopped):

    ```
    docker ps -a
    ```

    but when we use only ```docker ps``` without ```sudo``` we get permission denied error.

    For this, add ```user``` to the ```group(docker)``` by:

    ```
    cat /etc/group
    sudo usermod <user_name> -G <docker>
    ```

    To verify it's added or not type:

    ```
    sudo id <user_name>
    ```
    after this, logout from the ec2 enstance and login again.

    </br>

4. To check the storage occupied by a container:

    ```
    docker ps -as
    ```


5. Download the ```image``` on the docker host from the dockerhub:

    ```
    docker search <image_name> (search image on dockerhub)

    docker pull <image_name> (latest version is downloaded)
    docker pull <image_name>:<image_tag> (download specific verison)
    ```
    
    To see all the images in the docker host:

    ```
    docker image ls
    ``` 

    To remove an image not in use by container:

    ```
    docker rmi <image_name>:<image_tag>
    ```

    To remove an image forcefully, in use by any container:

    ```
    docker rmi -f <image_name>:<image_tag>
    ```

    ### Creating Container

    To create or deploy container in interactive mode which runs on the interface.
    In case of ```base/os image```
    
    ```
    docker run -it --name <container_name> <image_name> <execution command>

        eg. docker run -it --name mycontainer ubuntu bash
    ```

    </br>

    To create or deploy container in deattached mode which runs in the background.
    In case of only ```application image```
    
    ```
    docker run -d --name <container_name> <image_name> <execution command>

        eg. docker run -d --name mywebcontainer nginx
    ```

    To verify any application image has os and application both:

    ```
    -> login into the container.
    -> run the command: cat /etc/os-release (to check os)
    -> run the command: <application_name> -v (to check application)
    ```

    If we want to logout from the container: ```ctrl + p, ctrl + q```

    </br>

    To Stop the container:

    ```
    docker stop <container_name> or <container_id>
    ```

    To login back to the running container:

    ```
    docker exec -it <container_name> or <container_id> <executeable_command>

        eg. docker exec -it mycontainer bash
    ```

    To check container resource usage:

    ```
    docker stats (all running containers)
    docker stats <container_name/id> (for specific container)
    ```

    To remove the container from the docker host:

    ```
    docker stop <container_name/id>
    docker rm <container_name/id>
    ```

    To remove forcefully any container:

    ```
    docker rm -f <container_name/id>
    ```

    To rename the running container:
    
    ```
    docker rename <old_container_name> <new_container_name>
    ```