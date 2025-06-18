
## NPM
- `npm init`
	- Use `npm init -y` to acept all defaults
- creates basic package.json file in JSON format
- Dependencies are stored in the `node_modules` folder
	- this folder should be excluded from version control

## Adding Dependencies
- Two types
- Project dependencies
	- needed for the project to run
	- `npm install <dep>`
- Development dependencies
	- needed to support development
	- not used when the project is deployed
	- ex: testing libraries
	- `npm install <dep> --save-dev`

## Installing Listed Dependencies
- Many times, we'll receive an existing package.json files
- `npm install` will install all dependencies specified in package.json
- dependencies stored in local node_modules folder

## npm scripts
- Most package.json files will contain a scripts section
- You can run these using `npm run <name>`
	- eg. `npm run test`
- One exception: `start` script
	- If you have a script named start, you can run it via just npm start

## Example: express server
- express is a web server framework that runs on node.js
	- expressjs.com

- Javascript on the front-end and on the backend
- Install via `npm install express`
- then, in our code we can do:
	- `const express = require('express');`


# Docker Concepts & Architecture
- Platform for running apps in isolated software environments

## Docker Containers
- isolated software environment
- contains libraries, dependencies, executables, applications, etc.
- Like a lightweight virtual machine
- Its like a runnable instance of an image
- Each container is meant to run a single application or service, 
	- such as a web server or database server
- Usually configurable by passing in environment variables

## Docker Images
- Snapshot of an isolated filesystem of an application (template)
	- base software
	- application code and/or binaries
	- dependencies
	- configuration options
- Images have a name and can be tagged with different versions
	- eg, `httpd:latest`

## Docker Image Goals
- Some images are designed to be extended
	- linux distros
	- platforms/languages
- Others are designed to just be configured and run
	- Packaged apllications
	- eg. MySQL, Apache, NGINX, Minecraft


![[Pasted image 20250204231535.png]]

![[Pasted image 20250204231745.png]]

## Docker Networking
![[Pasted image 20250204231946.png]]

- Bridge
	- basically a network address translation 
	- provides private and internal IP for a virtual network in docker
- Host
	- sharing a connection with your computer
	- runs application directly on your machine
- Macvlan and ipvlan
	- connects network to your own router

![[Pasted image 20250204232250.png]]


# Building Images & Running Containers

## Running a container
- You can create a new container from an image
	- `docker run <image_name:tag>`
	- IF the image doesn't exist in the local cache, docker will try to download it
	- Docker will give the container a random name, or you can name it by passing the `--name` to the `docker run` command
- You can also start and stop existing containers
	- `docker stop <container_name>`
	- `docker start <container_name>`

## Docker Container Logs
- Each container should only run a single process
- This process should be run in the foreground 
	- as opposed to a background process, such as a daemon or service
	- Docker monitors the health of a process to determine the health of the container
- Process typically write to standard output and/or standard error
- `docker logs <container_name>` monitors the docker logs

## Custom Images: Dockerfile
- text file with instructions on how to build an image
- ![[Pasted image 20250204232833.png]]

![[Pasted image 20250204233059.png]]
- You muyst have at least a CMD or an ENTRYPOINT
- ENTRYPOINT runs before CMD
- Entrypoint provides a base executable, like a script you want to run, CMD provides arguments to the executable

![[Pasted image 20250204233536.png]]
![[Pasted image 20250204233635.png]]

![[Pasted image 20250204233837.png]]

- A volume is a folder or file that we link from the host into a specific location inside of the container
- means we can make changes to a file outside of the container and the changes will be reflected inside of the container
- means we dont have to rebuild the container each time we make changes


![[Pasted image 20250204233935.png]]
- We can forward a port from the host into a container. 

# Docker Compose
- A tool to manage multi-container applications, aka stacks
- Containers and stack settings are defined in a YAML file
	- compose.yml
- Run one command to build/start/stop all containers in the stack
- Each stack gets its own private network by default
![[Pasted image 20250204234216.png]]
![[Pasted image 20250316161903.png]]
![[Pasted image 20250204234405.png]]

![[Pasted image 20250204234610.png]]



Notes:
in the yaml files n stuff, everything on the left is on the host, everything on the right is on the container

ex. COPY . ./files
copies files from host to working directory on container

Source for a lot of errors:
- in the yaml file, be very specific with the volumes files
- If you mount the entire backend folder, instead of specific files, the dependencies in the node_modules folder are not added in there
- Only mount files that you are going to change


`RUN` executes commands during image build time, while `CMD`/`ENTRYPOINT` executes commands at container runtime
![[Pasted image 20250316162255.png]]
