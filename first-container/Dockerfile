# Test web app that returns the name of the host/pod/container servicing req
# Linux x64
#Start building this image by first grabing this image(line 4) a special container image with node tools pre-install, a foundation to build eveything on top
FROM node:current-alpine 

#Metadate
LABEL org.opencontainers.image.title="Hello Docker Learners!" \
      org.opencontainers.image.description="Web server showing host that responded" \
      org.opencontainers.image.authors="@nigelpoulton"

# Create directory in container image for app code
#In this new image make a new directory
RUN mkdir -p /usr/src/app

# Copy app code (.) to /usr/src/app in container image
#take all files and dirs from whereever we run the cmd can copy to the folder
COPY . /usr/src/app

# Set working directory context
WORKDIR /usr/src/app

# Install dependencies from packages.json
RUN npm install

# Command for container to execute
ENTRYPOINT [ "node", "app.js" ]