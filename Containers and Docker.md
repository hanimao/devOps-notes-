
What are containers?

- Lightweight portable units for running applications. They bundle an application with all its dependencies ensuring it runs consistently across different environments.
- They are isolated so it runs the same on any environment that i want to run it on ex my laptop, production environment.

Ex; I have an application and i want to run every part of the application. Containers will include the code, runtime, libraries including all the dependencies that the application needs to run. ![[Screenshot 2025-06-10 at 14.15.05.png]]


Docker engine ; makes the containersation possible. Provides the environment to build, run and manage containers. 


What is Docker?

An open platform for developing, shipping and running applications in containers. Simplifies the process of managing containers making it easier to build, deploy and run applications

Key component's

1. Docker Engine

Core service that runs and manage containers 

2. Docker Hub

A repository where you can find and share container images 

Images and Containers

What are images
- Templates that create the containers. It is a snapshot of the environment.
- Immutable - don't change once they're created. Applications runs consistently no matter where its deployed. 

Containers
- running instances of these images. Has everything that needs to run your application.

How do you create the images?

- A docker file is a file used to build docker images. Contains instructions that docker uses to create an image. 
- Allow for repeatable builds - create the exact same environment anywhere




![[Screenshot 2025-06-11 at 11.53.06.png]]



'run npm install' - tells you to install the node.js dependencies
EXPOSE 3000 - container will listen on the specified network port at runtime. Useful when you want to run the container and expose ports to the host machine.
1. Which image to use
2. Which files to copy to the container
3. Which commands to run in the container

**FIVE key Docker commands** 

1. **FROM** - specifies the base image to use for the docker image ex if you have a python image use a base image of python/version of python
2. **RUN** - executes commands in the container. Installs packages, update dependencies etc
3. **COPY** - copies files from the host machine into the container. This is how you bring your app code and configuration into the container.
4. WORKDIR - sets the working directory for subsequent instructions. Ensures that the command runs in the correct directory.
5. CMD - specifies the command to run when the container starts

Modern Development 

1. Simplified Deployment 
In software development one of the challenges is making sure applications work consistently across all environments.
2. Improved efficiency 
VM can be slow to start but containers are lightweight and shares the host system kernel 
3. Enhanced collaboration
Have the same environment, same application and docker image

Docker integrates smoothly with CI/CD pipelines allowing for automated testing, building and deployment of containers.


!!

![[Screenshot 2025-06-11 at 13.07.41.png]]

VM Vs Containers

VM 
1. Take minutes to startup
2. Consumes more resources
3. strong isolation
4. less portability

Containers
1. start within sec
2. resources efficient
3. process level isolation
4. high portability


**Create a simple python web application using flask to Dockerise**

What is flask?
- simple and lightweight framework for creating web applications in python. 

![[Screenshot 2025-06-13 at 14.29.20.png]]

importing flask - creating a new flask application instance
set a route - for the route to url which is forward slash here
app.run = running the server where app is just an instance of the flask. 
app = flask(name) - setting up the application instance defining what it can do
We are using the variable app and telling it to run on our local host (0.0.0.0) and doing it on port 5000.



![[Screenshot 2025-06-13 at 15.24.52.png]]
Command to run the application
python 3 app.py




![[Screenshot 2025-06-13 at 15.25.34.png]]
Docker Networking
- Default network options that you can use to manage how containers communicate with each other.
- Simplifies the implementation of microservices architecture. Microservices allow diff parts of an application to run as independent services each in its own container
- 

What is the difference between microservices and monolithic?

1. Bridge
- For containers on the same machine 
- Containers connected to the bridge can communicate with each other using their own IP addresses. 
- Isolated from your host machine network - extra layer of security.

2. Host Network (your laptop connected to your home wifi network)
- In host mode, a container uses the host machines network directly without any isolation. Its as if the container is plugged directly to your home network with no distinction between the container and the host 
- This mode is useful for app that need to closely interact with the host system

1. None(a room with no doors or windows)
- Containers has no network interface which makes it completely isolated. 
- no Network access


Docker compose

- Manages multiple containers docker applications 
- Imagine your app has several components/containers; web server, database and a caching service. Docker composes acts as the organiser ensuring they all work together smoothly 

key features
1. Docker-compose.yaml - list all the services your app needs. A blueprint that describes each container
2. commands - with a few commands you can start and stop and manage all your containers at once 
3. Networking - auto creates a network for your containers

Why is Docker compose important?

1. Makes dev and testing easier - dev can focus on writing more code and less of managing infrastructure
2. ensures consistency - everyone on your team is working in the same environment.
3. enhances teamwork

**Docker Hub**

Docker registries - Where does the docker image go after you built them
- Manage, store and deploy docker images
- Public and Private registries

Importance
- Streamline deployment - easily accessable and deployed across multiple environment from development to deployment.
- enhances collaboration - everyone on your team has access to the same resources. 
- ensures consistency. Push the image to the registry then pull the image to your pipeline.

Commands - pull and push images to docker hub.
- docker build -t username/flask-mysql:tagname . 
Build and tag it with your docker hub username and your repository that you just created. Tagname - version of the image 
. = use your current directory as the build context where it will look for the docker file
- docker push username/flask-mysql:tagname
- docker pull username/flask-mysql:tagname

How to push images to Amazon Elastic Container Registry (ECR)

ECR - storing and managing private docker images esp when you are working within the AWS ecosystem. 



