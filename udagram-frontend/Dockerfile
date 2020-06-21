# Use NodeJS base image
FROM node:13

# Install app dependencies by copying
# package.json and package-lock.json
RUN mkdir /udagram
WORKDIR /udagram

COPY package*.json /udagram/
COPY src /udagram/src/
COPY ionic.config.json /udagram
COPY angular.json /udagram
COPY tsconfig.json /udagram

# Install dependencies
# RUN npm install -g @ionic/cli
RUN npm install
RUN npm install -g ionic
RUN ionic build

# Bind the port that the image will run on
EXPOSE 8100

# Define the Docker image's behavior at runtime
CMD ["ionic", "serve", "--external"]
# ENTRYPOINT ["tail", "-f", "/dev/null"]