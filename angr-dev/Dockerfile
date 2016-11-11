FROM debian:latest

RUN apt-get update -y

RUN mkdir /root/angr-dev

RUN apt-get install -y  virtualenvwrapper python2.7-dev build-essential libxml2-dev libxslt1-dev git libffi-dev cmake libreadline-dev libtool debootstrap debian-archive-keyring libglib2.0-dev libpixman-1-dev

WORKDIR /root/angr-dev
