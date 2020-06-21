# Use NodeJS base image
FROM node:13

# Postgres Connection Settings
ARG POSTGRES_USERNAME=DEFAULT
ENV POSTGRES_USERNAME=$POSTGRES_USERNAME

ARG POSTGRES_PASSWORD=DEFAULT
ENV POSTGRES_PASSWORD=$POSTGRES_PASSWORD

ARG POSTGRES_DB=DEFAULT
ENV POSTGRES_DB=$POSTGRES_DB

ARG POSTGRES_HOST=DEFAULT
ENV POSTGRES_HOST=$POSTGRES_HOST

# AWS Settings
ARG AWS_REGION=DEFAULT
ENV AWS_REGION=$AWS_REGION

ARG AWS_PROFILE=DEFAULT
ENV AWS_PROFILE=$AWS_PROFILE

ARG AWS_BUCKET=DEFAULT
ENV AWS_BUCKET=$AWS_BUCKET

# JWT Token Generation Settings
ARG JWT_SECRET=DEFAULT
ENV JWT_SECRET=$JWT_SECRET


# Install app dependencies by copying
# package.json and package-lock.json
RUN mkdir /udagram-api-users
WORKDIR /udagram-api-users

COPY package*.json /udagram-api-users/
COPY src /udagram-api-users/src/
COPY tsconfig.json /udagram-api-users/

# Install dependencies
# RUN npm install -g @ionic/cli
RUN npm install

# Bind the port that the image will run on
EXPOSE 8100

# Define the Docker image's behavior at runtime
CMD ["npm", "run", "prod"]
