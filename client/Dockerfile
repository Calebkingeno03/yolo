# Stage 1: Build the application
FROM node:alpine as build

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install --production

# Copy the rest of the application code
COPY . .

# Build the application
RUN npm run build

# Stage 2: Serve the built application
FROM node:alpine

# Set the working directory
WORKDIR /app

# Copy built files from the previous stage
COPY --from=build /app/build ./build

# Expose the port on which your application runs
EXPOSE 3000

# Command to run the application
CMD ["node", "build/server.js"]
