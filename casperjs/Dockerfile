# casperjs
#
# Usage
#   docker run davidb583/casperjs casperjs --version
#   docker run cmfatih/phantomjs phantomjs --version

FROM ubuntu:14.04

MAINTAINER davidb583

# node + npm
RUN apt-get update
RUN DEBIAN_FRONTEND=noninteractive apt-get -qy dist-upgrade
RUN apt-get install -qy wget apt-transport-https
RUN apt-get update
RUN wget -qO- https://deb.nodesource.com/gpgkey/nodesource.gpg.key | apt-key add -
RUN echo 'deb https://deb.nodesource.com/node trusty main' > /etc/apt/sources.list.d/nodesource.list
RUN echo 'deb-src https://deb.nodesource.com/node trusty main' >> /etc/apt/sources.list.d/nodesource.list
RUN apt-get -qy install nodejs build-essential

# phantomjs 1.9.7
RUN apt-get install -y git-core curl libfreetype6 libfontconfig
RUN curl -LO https://bitbucket.org/ariya/phantomjs/downloads/phantomjs-1.9.7-linux-x86_64.tar.bz2
RUN tar xjfv phantomjs-1.9.7-linux-x86_64.tar.bz2 -C /usr/local/
RUN ln -sf /usr/local/phantomjs-1.9.7-linux-x86_64/bin/phantomjs /usr/local/bin/phantomjs

# python
RUN apt-get install -y python python-dev python-pip python-virtualenv
RUN   rm -rf  /var/lib/apt/lists/*

# casperjs 1.1.0-beta3
RUN npm install -g casperjs@1.1.0-beta3


