# Use an official Node.js runtime as a parent image
FROM node:14

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy the package.json and package-lock.json files
COPY package*.json ./

# Install any needed packages
RUN npm install

# Copy the rest of your application code
COPY . .

# Build the application for production
RUN npm run build

# Use an official Nginx image to serve the front end
FROM nginx:alpine

# Copy the built files from the previous stage to Nginx's public folder
COPY --from=0 /usr/src/app/build /usr/share/nginx/html

# Expose port 80
EXPOSE 80

# Command to run Nginx
CMD ["nginx", "-g", "daemon off;"]