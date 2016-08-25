
#
#MAINTAINER Chrlis.zhang
#DOCKER-VERSION         1.10.3
#
#Dockerizing jdk 1.7.0

#这里的c/centos:7.1 是构建基础镜像的名称
FROM c/centos:7.1


#java版本可以根据实际情况修改
ENV JAVA_VERSION 1.7.0
ENV JDK_HOME /usr/lib/jvm/java-1.7.0-openjdk


RUN yum install -y java-${JAVA_VERSION}-openjdk java-${JAVA_VERSION}-openjdk-devel && \
    yum clean all
