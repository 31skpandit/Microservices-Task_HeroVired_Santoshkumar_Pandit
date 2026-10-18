# Lightweight official Node.js LTS base image
FROM node:20-alpine

# Working directory inside the container
WORKDIR /usr/src/app

# Install dependencies first so this layer is cached between code changes
COPY package*.json ./
RUN npm install --omit=dev && npm cache clean --force

# Copy the application source
COPY . .

# Run as the non-root user that ships with the node image
USER node

# Port the service listens on
EXPOSE 3003

CMD ["node", "app.js"]
