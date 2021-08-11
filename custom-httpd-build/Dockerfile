#Acctually working only on podman due to OCP scc see https://access.redhat.com/solutions/2111281
FROM registry.access.redhat.com/ubi8/ubi
ENV SERVER_NAME=HTTPDTEST
LABEL Mantainer="csaggin" email=csaggin@redhat.com
RUN yum update --disablerepo=* --enablerepo=ubi-8-appstream --enablerepo=ubi-8-baseos -y && rm -rf /var/cache/yum
RUN yum install --disablerepo=* --enablerepo=ubi-8-appstream --enablerepo=ubi-8-baseos httpd -y && rm -rf /var/cache/yum
RUN mv /etc/httpd/conf.d/welcome.conf /etc/httpd/conf.d/welcome.backup
ADD https://raw.githubusercontent.com/RH-csaggin/custom-builds/master/custom-httpd-build/index.html /var/www/html/
RUN chmod 755 /var/www/html/index.html
EXPOSE 80
ENTRYPOINT ["/usr/sbin/httpd", "-D", "FOREGROUND"]