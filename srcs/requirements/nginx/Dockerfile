# srcs/requirements/nginx/Dockerfile

# Use a lightweight base image, either Alpine or Debian
FROM alpine:edge

# Install NGINX and OpenSSL (for TLS support)
RUN apk update && \
    apk add --no-cache nginx openssl

# Copy over the custom NGINX configuration
COPY conf/nginx.conf /etc/nginx/nginx.conf

# Copy SSL certificates (You’ll create these next)
COPY conf/certs/server.crt /etc/nginx/certs/server.crt
COPY conf/certs/server.key /etc/nginx/certs/server.key

# Expose port 443 for HTTPS traffic
EXPOSE 443

# Start NGINX in the foreground to ensure it runs as the main process
CMD ["nginx", "-g", "daemon off;"]

#CMD ["tail", "-f"]
