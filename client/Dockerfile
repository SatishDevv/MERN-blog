# Build stage
FROM node:21 AS build

# Set working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy the source code
COPY . .

# Build the React app
RUN npm run build

# Serve stage
FROM nginx:stable-alpine AS production

RUN rm -rf /usr/share/nginx/html/*

# Copy the built files from the build stage
COPY --from=build /app/dist /usr/share/nginx/html/


COPY /nginx/nginx.conf /etc/nginx/conf.d/default.conf

# Expose port 80
EXPOSE 80

# Start Nginx server
CMD ["nginx", "-g", "daemon off;"]
