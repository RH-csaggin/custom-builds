#Acctually working only on podman due to OCP scc see https://access.redhat.com/solutions/2111281
FROM kris-test/httpd-24-centos7:latest
ENV SERVER_NAME=HTTPDTEST
LABEL Mantainer="csaggin" email=csaggin@redhat.com
USER root
RUN yum update-minimal --security  -y && rm -rf /var/cache/yum
RUN rm -rf /etc/httpd
RUN yum install httpd24-httpd -y && \
    yum install epel-release -y && \
    yum install certbot certbot-apache -y && \
    rm -rf /var/cache/yum
ADD https://raw.githubusercontent.com/RH-csaggin/custom-builds/master/custom-httpd-build/index.html /var/www/html/index.html
RUN chmod 755 /var/www/html/index.html && \
    scl enable httpd24 bash && \
    rm -f /etc/httpd/conf.d/ssl.conf
    # certbot-auto --apache
EXPOSE 80
CMD sleep 3600
#ENTRYPOINT ["/opt/rh/httpd24/root/usr/sbin/httpd", "-D", "FOREGROUND"]