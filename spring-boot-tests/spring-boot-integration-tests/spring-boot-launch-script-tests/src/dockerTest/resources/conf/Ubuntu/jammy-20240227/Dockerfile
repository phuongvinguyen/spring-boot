FROM ubuntu:24.04 as prepare
COPY downloads/* /opt/download/
RUN mkdir -p /opt/jdk && \
    cd /opt/jdk && \
    tar xzf  /opt/download/* --strip-components=1

FROM ubuntu:24.04
RUN apt-get update && apt-get install -y software-properties-common curl
COPY --from=prepare /opt/jdk /opt/jdk
ENV JAVA_HOME /opt/jdk
ENV PATH $JAVA_HOME/bin:$PATH
