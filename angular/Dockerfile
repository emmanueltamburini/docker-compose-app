FROM nginx:stable-alpine

# Define volume
VOLUME /tmp

# Install web app on nginx server
RUN rm -rf /usr/share/nginx/html/*
COPY nginx.conf /etc/nginx/nginx.conf
COPY billingApp /usr/share/nginx/html
COPY mime.types /etc/nginx/mime.types

# The ports that it will show
EXPOSE 80

ENTRYPOINT [ "nginx", "-g", "daemon off;" ]