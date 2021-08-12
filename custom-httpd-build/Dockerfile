#Acctually working only on podman due to OCP scc see https://access.redhat.com/solutions/2111281
FROM registry.access.redhat.com/rhel7/rhel
ENV SERVER_NAME=HTTPDTEST
LABEL Mantainer="csaggin" email=csaggin@redhat.com
RUN yum -y update; yum clean all
RUN yum -y install httpd; yum clean all
ADD https://raw.githubusercontent.com/RH-csaggin/custom-builds/master/custom-httpd-build/index.html /var/www/html/index.html
RUN chmod 755 /var/www/html/index.html
EXPOSE 80
ENTRYPOINT ["/usr/sbin/httpd", "-D", "FOREGROUND"]