# Use an official Node.js image
FROM node:20

# Set the working directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json (if available)
COPY blog/package*.json ./

# Install Hexo and other dependencies
RUN npm install -g hexo-cli
RUN npm install

# Copy the entire blog directory
COPY blog/ .

# Build the Hexo site
RUN hexo generate

# Specify the command to run the Hexo server
CMD ["hexo", "server", "-H", "0.0.0.0"]
