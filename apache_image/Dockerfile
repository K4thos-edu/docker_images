FROM alpine:3.16

LABEL maintainer="K4 apache2 image"

RUN apk update --no-cache && apk add --no-cache apache2 apache2-utils

ADD subdir /var/www/localhost/htdocs/subdir

# Expose the port for access
EXPOSE 80

# Run the apache server
ENTRYPOINT ["/usr/sbin/httpd", "-D", "FOREGROUND"]
