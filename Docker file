FROM anapsix/alpine-java:latest

# Set environment
ENV JAVA_HOME /opt/jdk
ENV PATH ${PATH}:${JAVA_HOME}/bin
RUN apk update
RUN apk add wget
RUN wget -q  http://mirror.csclub.uwaterloo.ca/apache/zookeeper/zookeeper-3.4.9/zookeeper-3.4.9.tar.gz
RUN tar -xzf zookeeper-3.4.9.tar.gz -C /opt
RUN mv /opt/zookeeper-3.4.9 /opt/zookeeper
RUN cp /opt/zookeeper/conf/zoo_sample.cfg /opt/zookeeper/conf/zoo.cfg
EXPOSE 2181 2888 3888
WORKDIR /opt/zookeeper
VOLUME [/opt/zookeeper/conf, /tmp/zookeeper]
ENTRYPOINT ["/opt/zookeeper/bin/zkServer.sh", "start-foreground"]
