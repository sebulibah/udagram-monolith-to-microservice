FROM node:13-alpine

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies by copying
# package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install
RUN npm install -g ionic

# Copy app source
COPY . .
RUN ionic build

## Copy from from www to the html folder
FROM nginx:alpine
COPY --from=ionic  /usr/src/app/www /usr/share/nginx/html