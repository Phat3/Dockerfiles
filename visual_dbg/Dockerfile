FROM python_stack

RUN pip install flask

RUN pip install pusher

RUN useradd -m -s /bin/bash deploy

USER deploy

WORKDIR /home/deploy/

EXPOSE 5000

CMD python index.py