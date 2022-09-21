FROM alpine:3.16

LABEL maintainer="K4 nginx image"

RUN apk update --no-cache && apk add --no-cache nginx

COPY nginx.conf /etc/nginx/

COPY default.conf etc/nginx/http.d/

# Copy resources
ADD dir /var/lib/nginx/html/dir
ADD images /var/lib/nginx/html/images
ADD page_blue /var/lib/nginx/html/page_blue
ADD page_red /var/lib/nginx/html/page_red
COPY index.html /var/lib/nginx/html

# Expose the port for access
EXPOSE 80/tcp

# Run the nginx server
ENTRYPOINT ["nginx", "-g", "daemon off;"]
