#
#MAINTAINER	Chrlis.zhang
#DOCKER-VERSION		1.10.3
#
#Dockerizing CentOS7:Dockerfile for building CentOS images

#Centos版本
FROM centos:centos7.1.150


ENV TZ "Asia/shanghai"
ENV TERX xterm


#替换成阿里源，根据情况选择
#这个是直接网络上下载
#RUN yum install -y wget epel-release
#RUN mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
#RUN wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
#RUN yum makecache

#这个是把文件放到和Dockerfile一个目录
#ADD aliyun-mirror.repo /etc/yum.repos.d/CentOS-Base.repo
#ADD aliyun-epel.repo /etc/yum.repos.d/epel.repo

#yum安装一些软件，可以根据实际情况进行调整
RUN yum install -y curl wget lrzsz vim net-tools epel-release && \
    yum install -y gcc gcc-c++ make automake cmake python-devel libpng-devel libjpeg-devel && \
    yum install -y python-pip && \
    yum clean all

RUN pip install supervisor

ADD supervisord.conf /etc/supervisord.conf

RUN mkdir -p /etc/supervisor.conf.d && \
    mkdir -p /var/log/supervisor

EXPOSE 22

ENTRYPOINT ["/usr/bin/supervisord","-n","-c","/etc/supervisord.conf"] 
