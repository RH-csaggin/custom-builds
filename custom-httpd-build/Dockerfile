#Acctually working only on podman due to OCP scc see https://access.redhat.com/solutions/2111281
FROM centos:centos7
ENV SERVER_NAME=HTTPDTEST
LABEL Mantainer="csaggin" email=csaggin@redhat.com
USER root
RUN yum update -y && rm -rf /var/cache/yum
RUN yum install -y && rm -rf /var/cache/yum
ADD https://raw.githubusercontent.com/RH-csaggin/custom-builds/master/custom-httpd-build/index.html /var/www/html/index.html
RUN chmod 755 /var/www/html/index.html
EXPOSE 80
ENTRYPOINT ["/usr/sbin/httpd", "-D", "FOREGROUND"]