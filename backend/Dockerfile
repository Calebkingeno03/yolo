# Use the official Node.js image as base
FROM node:alpine

# Set the working directory inside the container
WORKDIR /

# Copy package.json and package-lock.json to the container
COPY package*.json ./

# Install dependencies based on package.json
RUN npm install

# Copy the rest of the application code to the container
COPY . .

# Expose port 5000 to allow outside connections
EXPOSE 5000

# Command to start the application when the container starts
CMD ["npm", "start"]
