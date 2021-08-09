FROM python:3-alpine
LABEL Mantainer="csaggin" email=csaggin@redhat.com
RUN mkdir /myvol
RUN echo "Bravo Pirla" > /myvol/pirla.txt
VOLUME /myvol
WORKDIR /tmp
ENV PYTHONUNBUFFERED=1
RUN adduser kris -D
ADD https://raw.githubusercontent.com/RH-csaggin/s2i-py-test/main/index.html /tmp/
EXPOSE 80
ENTRYPOINT [ "python", "-m", "http.server", "80" ]
