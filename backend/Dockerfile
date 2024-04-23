# Stage 1: Build backend
FROM node:21 AS backend-builder

# Set the working directory in the container
WORKDIR /app

# Copy only necessary JSON files for building
COPY package*.json ./

# Install dependencies
RUN npm i

# Copy the rest of the application code to the working directory
COPY . .

# Stage 2: Create production image
FROM node:21-slim

# Set the working directory in the container
WORKDIR /app

# Copy built application files from the previous stage
COPY --from=backend-builder /app .

# Copy necessary configuration files
COPY .env.sample .env

# Expose the port the app runs on (adjust if needed)
EXPOSE 5000

# Define the command to run the app
CMD ["npm", "start"]

