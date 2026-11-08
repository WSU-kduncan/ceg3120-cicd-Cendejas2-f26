# Project 6 - CI

## Part 1

**Dockerfile**

The [Dockerfile](./web-content/Dockerfile) included in our [web-content](./web-content) folder is the instruction to building our docker image. 
The instructions include `FROM httpd:2.4` which sets the base image of our own image as version 2.4 of the Apache HTTP Server.
Next is `COPY . /usr/local/apache2/htdocs/` which copies all files in the same directory as the Dockerfile to the default web directory.

**Build image**

To build an image using the Dockerfile, you will need to run a docker build command. In my own case I ran `docker build -t project6:1.0.0 .`. 
`-t` allows for naming of the image so it can be easily recognizable later. Then we name the image in my case I used `project6`, followed by `:1.0.0` for version control

**Run container**

To then run a container that will serve our web app from the image we built, we will need to run a docker run command. In my case, it was ` docker run -d -p 8080:80 --name project6 loosegoose38/project6:1.0.0`
`-d` runs the container in the background.
`-p 8080:80` connects our pc to the container, so 8080 is what we use on our web browser and 80 is the internal port the Apache web server is listening to.
`--name project` assigns the name to the container
`loosegoose38/projects6:1.0.0` is the image used to build the container.




![docker ps](./screenshots/dockerPs.png)
![apache up and running our web content](./screenshots/browser.png)
> The first screenshot shows our project 6 container containing our web-content is running. The second screenshot shows our html and css running on chrome, confirming that apache is serving our content.
