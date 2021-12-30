FROM registry.redhat.io/rhel8/httpd-24

# Add application sources
ADD https://raw.githubusercontent.com/RH-csaggin/git-test/main/index.html /src/index.html
RUN rm -rf /var/www/html && mv /src /var/www/html &&\
    find /var/www/html/ -type d -exec chmod 755 {} \; &&\
    chmod -R 777 /var/www/html/

# Run script uses standard ways to run the application
CMD run-httpd -T