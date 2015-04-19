FROM centos:6.6
MAINTAINER Filip Maretic "mareticfilip@gmail.com"

ENV PUPPET_VERSION 3.6.2

RUN rpm --import https://yum.puppetlabs.com/RPM-GPG-KEY-puppetlabs \
    && rpm -ivh http://yum.puppetlabs.com/puppetlabs-release-el-6.noarch.rpm
RUN rpm --import http://dl.fedoraproject.org/pub/epel/RPM-GPG-KEY-EPEL-6 \
    && rpm -Uvh http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm
RUN yum update -y && yum install -y \
    gcc \
    make \
    puppet-$PUPPET_VERSION \
    rubygems \
    ruby-devel \
    tar \
    && yum clean all 
RUN echo "gem: --no-ri --no-rdoc" > ~/.gemrc
RUN gem update --system && gem install \
    highline:"~>1.6.0" \
    librarian-puppet:"~>1"
CMD ["/bin/bash"]
