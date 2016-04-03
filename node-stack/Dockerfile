FROM debian

RUN apt-get install -y git

RUN apt-get -y update && \
	apt-get install -y nodejs && \
	apt-get install -y npm && \
	ln -s "$(which nodejs)" /usr/bin/node

RUN npm install -g bower

RUN useradd -m -s /bin/bash deploy

USER deploy

WORKDIR /home/deploy/



