FROM jenkins/jenkins

USER root

RUN apt-get update
RUN apt-get -y upgrade

RUN apt-get -y install curl software-properties-common
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash 

RUN apt -y install git vim build-essential nodejs valgrind cmake gcc default-jre default-jdk zip jq

RUN npm i newman -g

RUN apt-get update -qq \
    && apt-get install -qqy apt-transport-https ca-certificates curl gnupg2 software-properties-common
RUN curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add -
RUN add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/debian \
   $(lsb_release -cs) \
   stable"
RUN apt-get update  -qq \
    && apt-get install docker-ce=17.12.1~ce-0~debian -y
RUN usermod -aG docker jenkins

RUN wget "http://cdn.infra.tetel.in/bunnycdncli/nightly/bnycdn_0.0.2-1_amd64.deb"; dpkg -i bnycdn_0.0.2-1_amd64.deb

