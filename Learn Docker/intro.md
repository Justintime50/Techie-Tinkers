# Intro to Docker

Hey there, let's learn about Docker! Docker allows you to "securely build, share and run any application, anywhere." Docker does this by creating `containers` that your application runs in, similar to a `virtual machine`. You can call commands to build your application the exact same way, regardless of where it's running or on what device.

## Dockerfile

For the purposes of today's lesson, we won't dive into what a Dockerfile does. Simply put, a `Dockerfile` is the skeleton of commands for how to build a `Docker Image`.

## Docker Compose

Using the `docker-compose up -d` command in a terminal inside this project's directory will build a simple web application based on the criteria we provided in the `docker-compose.yaml` file. Feel free to check that file out and see what it does in depth! Essentially, we ask Docker to pull the latest Nginx image to serve our webpages and we ask Docker to pull the latest PHP image to interpret those files. Additionally, we tell Docker to persist our data in `volumes`, mounting a physical directory to a "virtual" directory inside the docker container. We also tell Nginx inside the docker container where it can pull the nginx configuration file. Finally, we link these two together so PHP and Nginx can work alongside each other.

##

There you have it! Docker allows for developers across operating systems, setups, and skill levels, to quickly and easily setup the scaffolding of their apps easily so that everyone's environment runs the exact same. Let's move on to the next section.
