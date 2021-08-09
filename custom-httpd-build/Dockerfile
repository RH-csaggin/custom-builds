FROM registry.access.redhat.com/ubi8/ubi
ENV ServerName=HTTPDTEST
LABEL Mantainer="csaggin" email=csaggin@redhat.com
RUN yum update --disablerepo=* --enablerepo=ubi-8-appstream --enablerepo=ubi-8-baseos -y && rm -rf /var/cache/yum
RUN yum install --disablerepo=* --enablerepo=ubi-8-appstream --enablerepo=ubi-8-baseos httpd -y && rm -rf /var/cache/yum
ADD https://raw.githubusercontent.com/RH-csaggin/custom-builds/master/custom-httpd-build/index.html /var/www/html/
RUN chmod 755 /var/www/html/index.html
EXPOSE 80
CMD ["-D", "FOREGROUND"]
ENTRYPOINT ["/usr/sbin/httpd"]
