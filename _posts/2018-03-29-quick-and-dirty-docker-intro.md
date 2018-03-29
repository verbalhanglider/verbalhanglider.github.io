# Introduction

[Docker](https://www.docker.com/community-edition) is a powerful tool for efficiently sharing environments for complicated applications -- namely web sites or applications -- that in the past has required lots of tedious setup

1. Find out all the required software to run the web site on your development machine
1. Search out the different software and make sure they have binaries to run on your machine
1. Install all the different software (if they even exist for the OS you are running) to your machine
1. Make sure it all runs correctly on your machine
1. Clone the repo to your machine
1. Install the code to your machine
1. Make sure that the code runs the way it is supposed to on your machine with all the new software you just installed
1. Get to work writing the new code that you were tasked to write by your manager

This is a tedious process taking upwards of a week to do that you could have been spending on more useful work that actually provided value for the organization. It's also a security problem because now (on top of all your other work) you are a system administrator in charge of keeping all that new software patched on your machine. 

You do keep constant vigilance about latest versions for all the software on your own workstation, right?

Well, Docker is here to save you from all of that. Now, the developer who starts the project just has to write one Dockerfile defining all the different software required to deploy the code -- defining a web server, any third-party libraries necessary, et cetera -- and then you (that developer's coworker) can deploy what she made and know that you are running what she intended you to run. 

Not to mention: when you're done with the docker container you just stop it and you no longer have a system administrator's headache of maintaining all the related software you had to install on your system doing things the old way. Once the container is down, it's as if all of that never existed on your machine

In this documentation, I will introduce the quick and dirty commands that you will need to get started with a dockerized project.

# Starting work with a Docker Container

You can do a lot with Docker, and it is an incredible tool to allow developers to collaborate on complicated projects, but most of the time you just need to get up and running ASAP so you can get some work done. So, here is the sequence of commands that you will most often use for dockerized projects that you come across.

- ```git clone git@github.com:uchicago-library/[repo name]``` or git clone https://github.com/uchicago-library/[repo name]``` to clone the project to your machine
- ```cd [repo name]``` to move into the newly created repo directory on your machine
- ```docker build . -t [a name that you will recognize two days later when you next look at the list of images]``` to build the container using the project's Dockerfile
- ```docker run [that name you just filled out after the -t option in in the docker build command]``` to run the container. 

For web sites or applications the variation of the command that you should use is:

- ```docker run -p 8000:80 -v $(pwd):/code [name of container]```

This will run the project in its docker container on port 80 but make it available to you on your machine on port 8000

It will also map the directory /code in the Docker container to your current working directory defined in ```$(pwd)```

# Ending work with a Docker container

Once you're done testing your docker container, you need to stop the container so that it frees up all resources being used -- like port numbers

- ```docker container ls``` will show the list of containers that you are running on your machine right now. You should look for the one that you started in order to test the project you're working on right now.
- ```docker container stop [identifier]``` will stop the container named [identifier]. The [identifier] is the value for the specific container found in the CONTAINER_ID column

Opptionally, if you think the docker image you built is hopelessly broken and you can't possibly debug so it's better just to nuke and start over you can

- ```docker rmi [image identifier]``` where [image identifier] is the IMAGE_ID of the image that you want to remove

## Handy commmands to keep at the ready

- ```docker ps -aq``` will list all the containers on your machine
- ```docker images -q``` will list all the images on your machine
- ``` docker stop $(docker ps -aq)``` will stop all containers on your system
- ```docker rm $(docker ps -aq)``` will remove all containers from your system
` ```docker rmi $(docker images -q)``` will remove all images from your system

