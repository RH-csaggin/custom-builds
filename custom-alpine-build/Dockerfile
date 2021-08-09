FROM python:3.6.14-alpine3.14
LABEL Mantainer="csaggin" email=csaggin@redhat.com
## RUN mkdir /myvol
RUN echo "Bravo Pirla" > /tmp/pirla.txt
WORKDIR /tmp
## RUN adduser kris -D ## For testing
ADD https://raw.githubusercontent.com/RH-csaggin/git-test/main/index.html /tmp
EXPOSE 8080
CMD [ "python", "-m", "http.server", "8080"]
