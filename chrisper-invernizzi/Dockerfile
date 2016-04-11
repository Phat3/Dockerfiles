FROM python_stack 

RUN apt-get install -y texlive-extra-utils

RUN pip install nltk

RUN pip install clint

RUN useradd -m -s /bin/bash deploy

USER deploy

WORKDIR /home/deploy/

RUN git clone https://github.com/invernizzi/Chrisper.git

RUN mkdir content

WORKDIR /home/deploy/Chrisper/

RUN ./chrisper 

CMD ./chrisper /home/deploy/content/*.tex

