FROM centos
LABEL maintainer="Camilo Vargas"
RUN sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-Linux-* &&\
 sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-Linux-*
RUN yum upgrade -y
RUN yum install httpd -y
COPY miweb/ /var/www/html/
RUN chmod -R 777 /var/www/html
EXPOSE 80
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]