FROM centos:6

USER root

RUN yum install java-1.7.0-openjdk-devel -y
RUN yum install unzip -y
RUN yum install zip -y
RUN yum install wget -y
RUN curl -s get.sdkman.io | bash
RUN export SDKMAN_DIR="$HOME/.sdkman"
RUN source "/root/.sdkman/bin/sdkman-init.sh"
RUN yes | /bin/bash -l -c 'sdk install groovy 1.8.6'
RUN yes | /bin/bash -l -c 'sdk install grails 1.3.9'
RUN yum install tk -y
RUN yum install autoconf cpio curl-devel expat-devel gcc gettext-devel make openssl-devel perl-ExtUtils-MakeMaker zlib-devel -y
RUN wget https://www.kernel.org/pub/software/scm/git/git-2.9.5.tar.gz
RUN tar xzf git-2.9.5.tar.gz
RUN cd git-2.9.5 && make configure
RUN ./git-2.9.5/configure --prefix=/usr/local
RUN cd git-2.9.5 && make install
RUN echo "export PATH=$PATH:/usr/local/git/bin" >> /etc/bashrc
RUN source /etc/bashrc
RUN yes | /bin/bash -l -c 'git --version'
RUN yum install tar -y
RUN yum install gzip -y
RUN yum install ca-certificates -y