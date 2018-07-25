FROM centos:6

USER root

RUN yum install java-1.7.0-openjdk-devel -y
RUN yum install unzip -y
RUN yum install zip -y
RUN yum install wget -y
RUN yum install ca-certificates -y && chown -R root:root /root
RUN yum install tk -y && chown -R root:root /root
RUN yum install autoconf cpio curl-devel expat-devel gcc gettext-devel make openssl-devel perl-ExtUtils-MakeMaker zlib-devel -y && chown -R root:root /root
RUN curl -s get.sdkman.io | bash
RUN export SDKMAN_DIR="$HOME/.sdkman"
RUN source "/root/.sdkman/bin/sdkman-init.sh"
RUN yes | /bin/bash -l -c 'sdk install groovy 1.8.6'
RUN yes | /bin/bash -l -c 'sdk install grails 1.3.9'
RUN wget https://www.kernel.org/pub/software/scm/git/git-2.9.5.tar.gz  && tar xzf git-2.9.5.tar.gz && cd git-2.9.5 && make configure && ./configure --prefix=/usr/local && make install && echo "export PATH=$PATH:/usr/local/git/bin" >> /etc/bashrc && cd .. && rm -rf git-2.9.5.tar.gz && rm -rf git-2.9.5 && chown -R root:root /root
RUN source /etc/bashrc
RUN yes | /bin/bash -l -c 'git --version'