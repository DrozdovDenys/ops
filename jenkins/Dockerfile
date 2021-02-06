FROM jenkins/jenkins:lts
USER root
RUN apt-get update
RUN apt-get -y install apt-transport-https ca-certificates curl gnupg2 software-properties-common
RUN curl -fsSL https://download.docker.com/linux/debian/gpg |  apt-key add -
RUN add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/debian \
   $(lsb_release -cs) \
   stable"
RUN apt-get update
RUN apt-get update && apt-get install -y maven
RUN apt-get install -y docker-ce=18.06.3~ce~3-0~debian
RUN apt-get clean
RUN rm -rf /var/lib/{apt,dpkg,cache,log}/
RUN usermod -G jenkins,docker jenkins
USER jenkins
