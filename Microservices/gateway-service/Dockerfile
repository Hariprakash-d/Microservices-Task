# Use an appropriate lightweight Node.js base image
FROM node:20-alpine

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy package dependency manifests first to leverage Docker cache layers
COPY package*.json ./

# Install application dependencies
RUN npm install --only=production

# Copy the rest of the microservice source code
COPY . .

# Expose the correct port for the User Service
EXPOSE 3003

# Valid CMD instruction to start the microservice
CMD ["node", "app.js"]
