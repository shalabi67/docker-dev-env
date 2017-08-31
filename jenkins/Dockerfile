FROM jenkins/jenkins:lts

USER root
RUN apt-get update \
      && apt-get install -y sudo \
      && rm -rf /var/lib/apt/lists/*

RUN echo "jenkins ALL=NOPASSWD: ALL" >> /etc/sudoers

ENV JENKINS_UC_LATEST=https://updates.jenkins.io/latest

#ARG docker_version=17.03.0~ce

#RUN curl -sSL https://get.docker.com/ | sh && \
#    apt-get purge -y docker-engine


# Add ourselves to the docker group so that we
# can use 'docker' commands without sudo.
#RUN adduser $USER docker

#RUN curl -sSL https://get.docker.com/ | sh && \
#    apt-get purge -y docker-engine && \
#    apt-get install docker-engine=${docker_version}-0~debian-jessie

#RUN curl -L https://github.com/docker/compose/releases/download/1.11.2/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose && \
#	chmod +x /usr/local/bin/docker-compose

#RUN usermod -aG docker jenkins

USER jenkins
COPY plugins.txt /usr/share/jenkins/plugins.txt
#COPY plugins.txt /usr/share/jenkins/plugins1.txt
#RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/plugins.txt
RUN /usr/local/bin/install-plugins.sh git maven gradle github bitbucket
#bitbucket github ssh-slaves email-ext pipeline-stage-view pipeline-github pipeline-maven timestamper
#scm-api credentials matrix-project display-url-api token-macro git ant

#COPY settings.xml /root/.m2/


#/var/jenkins_home/secrets/initialAdminPassword
