FROM node:13-alpine as build

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies by copying
# package.json and package-lock.json
COPY udagram-frontend/package*.json /usr/src/app/

# Install dependencies
RUN npm install -g ionic
RUN npm install

# Copy app source
COPY udagram-frontend/ /usr/src/app/
RUN ionic build

## Copy from from www to the html folder
FROM nginx:alpine
RUN rm -rf /usr/share/nginx/html/*
COPY --from=build /usr/src/app/www /usr/share/nginx/html