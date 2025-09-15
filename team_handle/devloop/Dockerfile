# syntax=docker/dockerfile:1.7

# Use a minimal Node.js image
FROM node:20-alpine

# Create app directory
WORKDIR /usr/src/app

# Install only production deps
COPY package.json package-lock.json* ./
RUN npm ci --only=production || npm ci

# Copy source
COPY server ./server

# Expose API port
EXPOSE 3000

# Ensure Node listens on all interfaces inside container
ENV HOST=0.0.0.0 PORT=3000 NODE_ENV=production

CMD ["node", "server/index.js"]

