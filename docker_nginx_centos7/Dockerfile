FROM centos:centos7

RUN yum update && yum install -y nginx
COPY html /var/www/html
# forward request and error logs to docker log collector
RUN ln -sf /dev/stdout /var/log/nginx/access.log \
&& ln -sf /dev/stderr /var/log/nginx/error.log
EXPOSE 80

STOPSIGNAL SIGTERM

CMD ["/usr/sbin/nginx", "-g", "daemon off;"]
