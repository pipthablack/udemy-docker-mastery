# Use the official Node.js image
FROM node:latest

# Install tini using the Debian package manager
RUN apt-get update && apt-get install -y tini && rm -rf /var/lib/apt/lists/*

# Set the working directory to /usr/src/app
WORKDIR /usr/src/app

# Copy package.json file to the working directory
COPY package.json .

# Install dependencies and clean the npm cache
RUN npm install && npm cache clean --force

# Copy all files from the current directory to the working directory
COPY . .

# Expose port 3000 from the container
EXPOSE 3000

# Start the container with the specified command
CMD [ "/usr/bin/tini", "--", "node", "./bin/www" ]
