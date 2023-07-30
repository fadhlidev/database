# SIMPLE DEVELOPMENT DATABASE ENVIRONMENTS

This is a simple database environment setup for software development that I usually use. The motivation is that I want to have a dedicated database instance for every software I develop (though sometimes it may not be necessary). Additionally, I do not want to set up a database IDE or tool for every DBMS I use, where I have to install specific software to manage or maintain the database.

So, I created these environments, which only require Docker installed on my system to set up the required databases. **Please keep in mind that this is my personal preference**.

Currently, I have four environment setups configured in a `docker-compose.yaml` file for different databases (mongodb, mysql, postgres, and redis). Each setup contains the database service itself and the service tool to manage the database, such as pgadmin for Postgres or phpmyadmin for MySQL.

## How To Use
Since every environment is configured using a Docker Compose file, please make sure that you have installed Docker and Docker Compose on your machine.

After that, please take a look at the `docker-compose.yaml` file of the database environment you want to run and change the configuration as needed, such as the username, password, the database name you want to use, and perhaps the port number of the service tool for that database. Also, note that for every image used, it is recommended to specify a specific version instead of using the `latest` tag for consistency.

Finally, follow these steps to run the environment:

1. Change the directory to the database you want to use, e.g., `postgres`.
    ```shell
    cd postgres
    ```

2. Create a `data` directory to store the database data, which will be bound to the database service container.
    ```shell
    mkdir data
    ```

3. Start the Docker Compose file using this command:
    ```shell
    docker-compose up
    ```
   You can also add the `-d` or `--detach` flag to run the services in the background.

4. To stop the running environment, you can press `CTRL+C`, or use this command if you ran it in detach mode:
    ```shell
    docker-compose down
    ```
