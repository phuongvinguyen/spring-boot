FROM redhat/ubi9:9.5-1741600006 as prepare
COPY downloads/* /opt/download/
RUN mkdir -p /opt/jdk && \
    cd /opt/jdk && \
    tar xzf  /opt/download/* --strip-components=1

FROM redhat/ubi9:9.5-1741600006
COPY --from=prepare /opt/jdk /opt/jdk
ENV JAVA_HOME /opt/jdk
ENV PATH $JAVA_HOME/bin:$PATH
