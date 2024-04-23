# Stage 1: Build frontend
FROM node:21 AS frontend-builder

# Set the working directory in the container
WORKDIR /app

# Copy package.json, package-lock.json, and any other JSON files to the working directory
COPY *.json ./

# Install dependencies
RUN npm ci

# Stage 2: Create production image
FROM node:21-slim

# Set the working directory in the container
WORKDIR /app

# Copy built application files from the previous stage
COPY --from=frontend-builder /app .

# Expose the port the app runs on
EXPOSE 5173

# Define the command to run the app
CMD ["npm", "run", "dev", "--", "--host"]

