FROM nginx:latest
COPY web.html /app
EXPOSE 80
CMD [ "nginx", "-g", "daemon off;"]


 # Stage 1: Build the React app
#FROM node:18 AS builder

WORKDIR /app
#COPY package.json package-lock.json ./
#RUN npm install
COPY . .
RUN sudo apt update 

# Stage 2: Serve the built files with Nginx
FROM nginx:latest

# Copy built files from builder stage
COPY --from=builder /app/build /usr/share/nginx/html

# Expose port 80 and start Nginx
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"] 
