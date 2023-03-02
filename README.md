# docker-example2

## Setup

Build the container image using the following commands:

In the terminal, change directory to the docker-example2/app directory. Replace /path/to/app with the path to your docker-example2/app directory.

1. cd /path/to/app

Build the container image.

2. docker build -t docker-example2 .

The docker build command uses the Dockerfile to build a new container image. You might have noticed that Docker downloaded a lot of “layers”. This is because you instructed the builder that you wanted to start from the node:18-alpine image. But, since you didn’t have that on your machine, Docker needed to download the image.

After Docker downloaded the image, the instructions from the Dockerfile copied in your application and used yarn to install your application’s dependencies. The CMD directive specifies the default command to run when starting a container from this image.

Finally, the -t flag tags your image. Think of this simply as a human-readable name for the final image. Since you named the image docker-example2, you can refer to that image when you run a container.

The . at the end of the docker build command tells Docker that it should look for the Dockerfile in the current directory.

## Start

Now that you have an image, you can run the application in a container. To do so, you will use the docker run command.

Start your container using the docker run command and specify the name of the image you just created:

1. docker run -dp 3000:3000 docker-example2

2. After a few seconds, open your web browser to http://localhost:3000. You should see your app.

## Pull

docker pull kimelet/getting-started-exp1
