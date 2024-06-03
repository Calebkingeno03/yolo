# Use node alpine image as base
FROM node:alpine

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package.json package-lock.json ./

# Install all dependencies (including devDependencies for building)
RUN npm install

# Copy the rest of the application code
COPY . ./

# Build the application
RUN npm run build

# Expose the port on which your application runs
EXPOSE 3000

# Command to run the application
CMD ["node", "build/server.js"]
