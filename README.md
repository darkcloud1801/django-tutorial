# django-tutorial

This tutorial is just a Django base template for running django tutorial in a self contained environment.

## Installation

1. [Docker for Mac](https://docs.docker.com/docker-for-mac/install/)
2. Fork or Clone [Django Tutorial Repository](https://github.com/darkcloud1801/django-tutorial.git)

## Set Up

1. Change directory to Django Tutorial root directory
   ```commandline
   cd ~/Projects/django-tutorial
   ```


2. Run docker-compose
   > The -d lets you run the containers detached so you can continue to use the same terminal
   > otherwise you may elect to remove -d and open a new shell.

   ```commandline
   docker-compose up -d
   ```

3. Test your server. Open a browser and see your new [Django Application](http://localhost:8000)

4. Identify the Web Container.
   > Change to the project directory and list out all running containers. Copy the ID of the container
   > whose name ends in `_web`.
   ```commandline
   docker ps
   ```

5. SSH into the Web Container
   > After you are in the container, you can execute commands fron within the root directory `/code`.
   ```commandline
   docker exec -it <web_container_id> bash
   ```

6. Start the [Django Tutorial](https://docs.djangoproject.com/en/3.1/intro/tutorial01/#creating-the-polls-app)
   > Most commands will need to be run within the web container.

   ```

## Troubleshooting

1. If you have an issue performing a docker-compose down from pycharm, close pycharm, navigate to the project in the
   terminal, and execute:
   > docker ps -a | grep -i pycharm | awk '{print $1}' | xargs docker rm