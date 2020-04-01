# Intro to Docker

Let's learn about Docker! Docker allows you to "securely build, share and run any application, anywhere." Docker does this by creating `containers` that your application runs inside of, similar to a `virtual machine` running an operating system. You can call commands to build your application the exact same way, regardless of where it's running or on what device.

## Installation

Let's start by [installing Docker](https://docs.docker.com/install/). Once you've installed Docker, run the following command in a terminal: `docker run hello-world`. If you installed this correctly, Docker will start a simple "Hello World" container.

## Dockerfile

A Dockerfile is how your image is implemented. This allows you to grab a base `image`, let's say `php-7.4`, and configure it to your needs. Let's say you needed a PHP extension or wanted to add a web server such as `nginx`. You can do all of this with a Dockerfile.

## Docker Compose

Using the `docker-compose up -d` command in a terminal inside this project's directory will build a simple web application based on the criteria we provided in the `docker-compose.yaml` file. Feel free to check that file out and see what it does in depth. 

Essentially, we ask Docker to pull the latest `Nginx` image to serve our webpages and we ask Docker to pull the latest `PHP` image to interpret those files. Additionally, we tell Docker to persist our data in `volumes`, mounting a physical directory to a "virtual" directory inside the docker container. We also tell Nginx inside the docker container where it can pull the nginx configuration file. Finally, we link these two together so PHP and Nginx can work alongside each other.

## Conclusion

There you have it! Docker allows for developers across operating systems, environments, and skill levels, to quickly and easily setup the scaffolding of their apps easily so that everyone's environment runs the exact same.
