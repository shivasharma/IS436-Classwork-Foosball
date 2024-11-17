
# Use the official Nginx base image
FROM nginx:latest

# Copy the HTML files to the nginx html directory
COPY . /usr/share/nginx/html

# Expose port 80
EXPOSE 80
# Set a non-root user ID (UID)
RUN useradd -u 1001 -d /home/nginx -m -s /sbin/nologin nginx || true

# Adjust permissions for directories required by Nginx
RUN mkdir -p /var/cache/nginx /var/run /var/log/nginx && \
    chown -R nginx:nginx /var/cache/nginx /var/run /var/log/nginx /etc/nginx && \
    chmod -R 775 /var/cache/nginx /var/run /var/log/nginx /etc/nginx

# Switch to the non-root user
USER 1001

# Expose Nginx default port
EXPOSE 80

# Run Nginx
CMD ["nginx", "-g", "daemon off;"]
