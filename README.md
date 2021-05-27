# deephaven-compose
Deephaven Docker Compose Examples

### Workflow

* Download the latest images:
    ```sh
    docker-compose pull
    ```

* Create project:
    ```sh
    docker-compose up -d
    ```
* Connect to the web IDE at [http://localhost:10000](http://localhost:10000)

* List the state of the containers:
    ```sh
    docker-compose ps
    ```

* Follow the logs of all containers:
    ```sh
    docker-compose logs -f
    ```
    Control-c to exit.

* Follow the logs of a specific container:
    ```sh
    docker-compose logs -f grpc-api
    ```
    Control-c to exit.

* Destroy all containers:
    ```sh
    docker-compose down
    ```

### Tips and tricks

* Project name:
    Add `-p <project-name>` to your docker-compose commands to give your project a more meaningful name. For example:
    ```sh
    docker-compose -p my-first-project up -d
    ```
    Alternatively, you may use the `COMPOSE_PROJECT_NAME` environment variable.
    ```sh
    export COMPOSE_PROJECT_NAME=my-first-project
    docker-compose up -d
    ```

* Port:
    Set the `PORT` environment variable to select a different port. For example:
    ```sh
    export PORT=10001
    docker-compose up -d
    ```

* Multiple projects:
    Set a project name and port to spin up multiple projects at the same time:
    ```sh
    PORT=10001 docker-compose -p foo-project up -d
    PORT=10002 docker-compose -p bar-project up -d
    ```

* Set a specific version:
    Set the `VERSION` environment variable to select a different docker tag. For example:
    ```sh
    export VERSION=0.0.2
    docker-compose up -d
    ```
