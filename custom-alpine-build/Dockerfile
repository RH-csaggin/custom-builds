FROM registry.redhat.io/rhel8/httpd-24

# Add application sources
ADD https://raw.githubusercontent.com/RH-csaggin/git-test/main/index.html /var/www/html/index.html

# Run script uses standard ways to run the application
CMD run-httpd -T