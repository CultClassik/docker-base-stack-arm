FROM lsioarmhf/nginx-aarch64
 
MAINTAINER Chris Diehl <cultclassik@gmail.com>

# NEED TO PURGE APK CACHE
RUN apk --no-cache add curl
  
RUN mkdir -p /etc/docker-gen/templates && cd /etc/docker-gen/templates

RUN curl -o /etc/docker-gen/templates/nginx.tmpl https://raw.githubusercontent.com/jwilder/docker-gen/master/templates/nginx.tmpl 

