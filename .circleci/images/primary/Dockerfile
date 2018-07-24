FROM centos:6

USER root

RUN yum install java-1.7.0-openjdk-devel -y
RUN yum install unzip -y
RUN yum install zip -y
RUN curl -s get.sdkman.io | bash
RUN export SDKMAN_DIR="$HOME/.sdkman"
RUN source "/root/.sdkman/bin/sdkman-init.sh"
RUN yes | /bin/bash -l -c 'sdk install groovy 1.8.6'
RUN yes | /bin/bash -l -c 'sdk install grails 1.3.9'
RUN yum install git -y
RUN yum install tar -y
RUN yum install gzip -y
RUN yum install ca-certificates -y