FROM jenkins/jnlp-slave:3.27-1-alpine

USER root

COPY kubectl /usr/local/bin
COPY helm /usr/local/bin

# ant
RUN wget -q http://mirrors.tuna.tsinghua.edu.cn/apache//ant/binaries/apache-ant-1.10.6-bin.tar.gz && \
    tar -xzf apache-ant-1.10.6-bin.tar.gz && \
    mkdir /opt && mv apache-ant-1.10.6 /opt/ant && \
    rm apache-ant-1.10.6-bin.tar.gz
ENV ANT_HOME /opt/ant
ENV PATH ${PATH}:/opt/ant/bin

# docker
COPY docker.tgz docker.tgz
RUN tar --strip-components=1 -xzvf docker.tgz -C /usr/local/bin && rm docker.tgz
