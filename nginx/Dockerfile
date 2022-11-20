FROM nginx:1.23.2-alpine

# Install NGINX
RUN apk update
RUN apk add nginx

# Remove default files we don't need
RUN rm /etc/nginx/conf.d/default.conf

# Add default configuration
COPY conf/jenkins.conf /etc/nginx/conf.d/jenkins.conf
COPY conf/nginx.conf /etc/nginx/nginx.conf

EXPOSE 80

CMD ["nginx"]