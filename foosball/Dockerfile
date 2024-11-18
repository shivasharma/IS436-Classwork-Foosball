
FROM nginx:1.26.0-alpine

# Remove default welcome page
RUN rm /usr/share/nginx/html/index.html

# 1. support running as arbitrary user which belogs to the root group
# 2. users are not allowed to listen on priviliged ports
# 3. comment user directive as master process is run as user in OpenShift anyhow

EXPOSE 80
# Copy the HTML files to the nginx html directory
COPY . /usr/share/nginx/html

USER nginx