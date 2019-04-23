FROM jenkins/jnlp-slave:3.27-1-alpine

USER root

COPY kubectl /usr/local/bin
COPY helm /usr/local/bin

# docker
COPY docker.tgz docker.tgz
RUN tar --strip-components=1 -xzvf docker.tgz -C /usr/local/bin && rm docker.tgz
