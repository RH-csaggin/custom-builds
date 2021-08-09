FROM registry.redhat.io/rhel7/rhel-atomic
LABEL Mantainer="csaggin" email=csaggin@redhat.com
RUN mkdir /myvol
RUN echo "Bravo Pirla" > /myvol/pirla.txt
VOLUME /myvol
WORKDIR /tmp
ENV PYTHONUNBUFFERED=1
## RUN adduser kris -D ## For testing
ADD https://raw.githubusercontent.com/RH-csaggin/git-test/main/index.html /tmp/
EXPOSE 80
ENTRYPOINT [ "python", "-m", "http.server", "80" ]
