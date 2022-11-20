
FROM jenkins/jenkins:2.361.4-jdk11
USER root
RUN apt-get update && apt-get install -y lsb-release
RUN curl -fsSLo /usr/share/keyrings/docker-archive-keyring.asc \
  https://download.docker.com/linux/debian/gpg
RUN echo "deb [arch=$(dpkg --print-architecture) \
  signed-by=/usr/share/keyrings/docker-archive-keyring.asc] \
  https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" > /etc/apt/sources.list.d/docker.list
RUN apt-get update && apt-get install -y docker-ce-cli
USER jenkins
RUN jenkins-plugin-cli --plugins "blueocean:1.25.8 docker-workflow:521.v1a_a_dd2073b_2e"















# FROM jenkins/jenkins:alpine-jdk11
# 
# # Prep Jenkins Directories
# USER root
# RUN mkdir /var/log/jenkins
# RUN mkdir /var/cache/jenkins
# RUN chown -R jenkins:jenkins /var/log/jenkins
# RUN chown -R jenkins:jenkins /var/cache/jenkins
# USER jenkins
# 
# EXPOSE 8080
# 
# # Set Defaults
# ENV JAVA_OPTS="-Xmx8192m"
# ENV JENKINS_OPTS="--handlerCountMax=300  --webroot=/var/cache/jenkins/war" 