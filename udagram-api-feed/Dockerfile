FROM node:13

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies by copying
# package.json and package-lock.json
COPY udagram-api-feed/package*.json /usr/src/app/

# Install dependencies
RUN npm install

# Copy app source
COPY udagram-api-feed /usr/src/app

# Bind the port that the image will run on
EXPOSE 8080

# Define the Docker image's behavior at runtime
CMD [ "npm", "run", "prod" ]
