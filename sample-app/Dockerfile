FROM nginx:1.16.1-alpine

# We need to give all user groups write permission on folder /var/cache/nginx/ and file /var/run/nginx.pid.
# So users with random uid will be able to run NGINX.
RUN chmod -R a+w /var/cache/nginx/ \
        && touch /var/run/nginx.pid \
        && chmod a+w /var/run/nginx.pid \
        && rm /etc/nginx/conf.d/*

COPY sample-app/hello.conf /etc/nginx/conf.d/
COPY sample-app/index.html /usr/share/nginx/html/
EXPOSE 8080
USER nginx
