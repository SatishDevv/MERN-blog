# Build stage
FROM node:21-alpine

# Set working directory
WORKDIR /app

COPY package*.json ./

RUN npm install --production

# Copy the source code
COPY . .
ENV NODE_ENV=production

# Expose port 80
EXPOSE 8080

# Start
CMD ["npm", "start"]
