# Use an official Node.js runtime as a parent image
FROM node:21

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY . .

# Install dependencies
RUN npm i

# Copy the rest of the application code to the working directory
COPY .env.sample .env

# Expose the port the app runs on
EXPOSE 5000

# Define the command to run the app
CMD [ "npm", "start" ]

