# Description: Dockerfile for the foosball web application
FROM nginx:latest

# Copy the HTML files to the nginx html directory
COPY . /usr/share/nginx/html

# Create necessary directories and set permissions
RUN mkdir -p /var/cache/nginx /var/run /var/log/nginx && \
    chmod -R 775 /var/cache/nginx /var/run /var/log/nginx /etc/nginx && \
    chown -R 1001:0 /var/cache/nginx /var/run /var/log/nginx /etc/nginx

# Remove or comment out the 'user' directive in the config
RUN sed -i 's/^user/#user/' /etc/nginx/nginx.conf

# Use a non-root user
USER 1001

# Expose default HTTP port
EXPOSE 80

# Run Nginx
CMD ["nginx", "-g", "daemon off;"]
