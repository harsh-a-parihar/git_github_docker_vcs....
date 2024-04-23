# Create your own image
-----------------------

### Step.1

1. Create a container, run application and deploy it on the server.

    - [how to deploy application on the container](docker/how_deploy_app_on_container.md)

### Step.2

1. Create image of the container.

    ```
    docker commit <container_name/id> <image_name>
    ```

2. Check image has been created.

    ```
    docker image ls
    ```

### Step.3

1. Now, create account on the [Dokerhub](https://hub.docker.com/) and login into it.

2. Create a new respository for the image.

3. Come back to docker, and tag the image by:

    ```
    docker tag <image_name> <dockerhub_username/repository_name>:latest
    docker image ls -a      # check image
    ```

4. Now, to push the image on the dockerhub, login into docker from ec2:

    ```
    docker login
    Username: <dockerhub_username>
    Password: <dockerhub_password>
    ```

5. After login, push the image on the docker hub:

    ```
    docker push <dockerhub_user/repository_name>:latest
    ```

    check the repository, your application's image is created.

### Run the application on the container...

- (Optional) You can delete every other image and stopped containers..

    ```
    docker system prune -fa
    ```

- Pull the image you created.

    ```
    docker pull <username/repository_name>          # image_name: <dockerhub_username/repository_name>
    ```

- aunch a container with the image and map port, and just access it on browser.

    ```
    docker run -d --name <container_name> -p 80:80 <image_name>
    ```

