FROM registry.access.redhat.com/rhscl/python-36-rhel7
LABEL Mantainer="csaggin" email=csaggin@redhat.com
## RUN mkdir /myvol
RUN echo "Bravo Pirla" > /tmp/pirla.txt
WORKDIR /tmp
ENV PYTHONUNBUFFERED=1
## RUN adduser kris -D ## For testing
ADD https://raw.githubusercontent.com/RH-csaggin/git-test/main/index.html /var/www/html/
EXPOSE 8080
ENTRYPOINT [ "python", "-m", "http.server", "8080" ]
