FROM centos:6

USER root

RUN yum install java-1.7.0-openjdk-devel -y
RUN yum install unzip -y
RUN yum install zip -y
RUN yum install wget -y
RUN yum install ca-certificates -y && chown -R root:root /root
RUN yum install tk -y && chown -R root:root /root
RUN yum install autoconf cpio curl-devel expat-devel gcc gettext-devel make openssl-devel perl-ExtUtils-MakeMaker zlib-devel -y && chown -R root:root /root
RUN cd /usr/local && mkdir grails && cd grails && wget http://dist.springframework.org.s3.amazonaws.com/release/GRAILS/grails-1.3.9.zip && unzip grails-1.3.9.zip && rm grails-1.3.9.zip 
RUN echo $JAVA_HOME
RUN echo "export JAVA_HOME=/usr/lib/jvm/java-1.7.0-openjdk-1.7.0.181.x86_64" >> /etc/profile && source /etc/profile && echo $JAVA_HOME
RUN echo "export GRAILS_HOME=/usr/local/grails/grails-1.3.9" >> /etc/profile && source /etc/profile && echo $GRAILS_HOME && echo "export PATH=$PATH:/usr/local/grails/grails-1.3.9/bin" >> /etc/bashrc && source /etc/bashrc
RUN yes | /bin/bash -l -c 'grails help'
RUN wget https://www.kernel.org/pub/software/scm/git/git-2.9.5.tar.gz  && tar xzf git-2.9.5.tar.gz && cd git-2.9.5 && make configure && ./configure --prefix=/usr/local && make install && echo "export PATH=$PATH:/usr/local/git/bin" >> /etc/bashrc && cd .. && rm -rf git-2.9.5.tar.gz && rm -rf git-2.9.5 && chown -R root:root /root
RUN source /etc/bashrc
RUN yes | /bin/bash -l -c 'git --version'
RUN ls /usr/lib/jvm/java-1.7.0-openjdk-1.7.0.181.x86_64