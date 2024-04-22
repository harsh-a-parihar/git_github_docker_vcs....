# How to deploy any application on a container (manual way)
-----------------------------------------------------------

## Step 1:

- Create a container and map the port of the container to the host machine.

    ```
    docker run -d --name <container_name> -p 8080:80 <image_name>       # 8080: port of host machine, 80: port of container
    ```
    docker run -it <container_name> bash
    ```

## Step 2:

- Install the required software in the container.

    ```
    apt-get update -y
    apt-get install <software_name>     # e.g. apache2, nginx, etc.
    ```

## Step 3:

- Copy the application files to the container.

    1. Copy the application files to the container using docker cp command. Note: docker commands does not run in container, it runs on host machine.

        ```
        docker cp <source_path> <container_name>:</var/www/html>    # /var/www/html: destination path in the container
        ```

    2. Install 'git' in the container and clone the application respository.
    
        ```
        apt-get install git
        git clone <repository_url>      # should be done at destination path(/var/www/html) in the container
        ```

## Step 4:

- Start the application server in the container.

    ```
    /etc/init.d/<service_name> start    # service_name: apache2, etc.
    ```
    OR

    for linux based servrers use:

    ```
    systemctl start <service_name> 
    ```

## Step 5:

- Access the application using the host machine's IP address and port number.

    ```
    http://<host_ip>:8080
    ```