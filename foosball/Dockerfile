
FROM nginx:alpine  # or whatever base you're using

# Make nginx directories writable for any user
RUN mkdir -p /var/cache/nginx /var/run /var/log/nginx \
    && chmod -R g+rwX /var/cache/nginx /var/run /var/log/nginx /etc/nginx/conf.d

# Allow random OpenShift user to own the group
USER 1001


COPY . /usr/share/nginx/html

