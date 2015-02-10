FROM centos:6
MAINTAINER Filip Maretic <mareticfilip@gmail.com>

# Setup environment variables
ENV JAVA_VERSION 1.7.0

# Update and install java-openjdk
RUN yum update -y && yum install -y java-$JAVA_VERSION-openjdk

# Install supervisor
WORKDIR /tmp
RUN curl https://bootstrap.pypa.io/ez_setup.py -o - | python
RUN easy_install supervisor

# Supervisor configuration is set via supervisord.conf file
# To run supervisord in foreground set nodaemon=true
COPY supervisord.conf /etc/

# Default command
CMD ["supervisord", "-c", "/etc/supervisord.conf"]
