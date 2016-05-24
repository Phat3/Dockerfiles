FROM kalilinux/kali-linux-docker

# install main dependecies
RUN apt-get update -y && \
	apt-get install -y metasploit-framework && \
	apt-get install -y git && \
	apt-get install -y gdb

# install python env
RUN sudo apt-get install -y python-pip python-dev build-essential

# install zsh
RUN apt-get install -y zsh

# install compatibility libs for 32bit
RUN apt-get install -y lib32z1 lib32ncurses5

# create the user
RUN useradd -m -s /usr/bin/zsh phate

# add some custom utilities
ADD ./utils/* /usr/local/bin/ 

RUN chmod +x -R /usr/local/bin/

USER phate

WORKDIR /home/phate

# install oh-my-zsh
ENV TERM="xterm"

RUN wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh || true

# install capstone
RUN git clone --progress --verbose https://github.com/aquynh/capstone.git

RUN cd capstone && ./make.sh

USER root

RUN cd capstone && ./make.sh install

# install ropper
RUN pip install ropper

USER phate

CMD zsh

