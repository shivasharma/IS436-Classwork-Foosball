# Use an official nginx image as the base image
FROM nginx:alpine

# Copy the HTML files to the nginx html directory
COPY . /usr/share/nginx/html

# Expose port 80
EXPOSE 80

# Start nginx when the container starts
CMD ["nginx", "-g", "daemon off;"]

RUN mkdir -p /var/cache/nginx && \
    chmod -R 777 /var/cache/nginx

RUN useradd -u 1001 nginx
USER 1001
