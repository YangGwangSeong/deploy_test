# Base image
FROM node:16.14.2-alpine

# Create app directory
WORKDIR /app

# A wildcard is used to ensure both package.json AND package-lock.json are copied
COPY ./package*.json ./

# Install app dependencies
RUN npm install

# Bundle app source
COPY . .

# Creates a "dist" folder with the production build
RUN npm run build

COPY . .

# Start the server using the production build
CMD [ "node", "dist/main.js" ]

