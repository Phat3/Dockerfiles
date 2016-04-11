FROM kalilinux/kali-linux-docker

RUN apt-get update -y && apt-get install -y metasploit-framework

RUN apt-get install -y zsh

RUN useradd -m -s /bin/zsh phate

USER phate

WORKDIR /home/phate

# RUN touch ~/.zshrc && sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

