# Fork the repo and clone into the machine
fork the repo to your github account and Git clone to your machine.
# Docker Files Creation
# Explanation
## Base image used

` FROM node:16.17.1-alpine3.16 ` - Alpine image is fast and very small in size

## Dockerfile directives

` FROM node:16.17.1-alpine3.16` -  Alpine base image to build from

` WORKDIR /usr/src/(client | backend) ` - A working directory to hold application code

` COPY package*.json ./ ` - Copy ` package.json ` and ` package-lock.json ` files containing project dependencies to the working directory inside the docker image

` RUN npm install ` - Install project dependencies

` COPY . . ` -  Copy project source code to the working directory inside the docker image

` RUN npm run build ` - Compile project for production

` EXPOSE 3000 ` - Expose port 3000 for client and 5000 for backend

` CMD ["node", "server.js"] ` or ` CMD [ "serve", "-s", "build", "-l", "3000" ] ` - Start the server

# Instructions

1. Clone this repository ` https://github.com/rodneykabiru/yolo `
2. Change in to yolo directory ` cd yolo `
3. Run docker compose ` docker-compose up --build `
    - You can pass ` -d ` to the above command if you want to run in detached mode

If you need to go inside a container run the following command
    ` docker exec -it <container id> /bin/bash `
    - Run ` docker ps ` to get the container ID

To view container logs
    ` docker logs <container id> `

# DOCKER HUB
[yolo client](https://hub.docker.com/r/rodney080/client)
[yolo backend](https://hub.docker.com/r/rodney080/backend)