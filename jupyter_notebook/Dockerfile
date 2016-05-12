FROM debian_custom

# Install dependencies for anaconda
RUN apt-get install -y bzip2

# Install everythin as an unprivilege user
RUN useradd -m -s /bin/bash deploy

USER deploy

WORKDIR /home/deploy/

# Download the latest version of anaconda
RUN wget http://repo.continuum.io/archive/Anaconda3-4.0.0-Linux-x86_64.sh

# Install anaconda
RUN bash Anaconda3-4.0.0-Linux-x86_64.sh -b

# Install jupyter notebook
RUN ./anaconda3/bin/conda install jupyter

# Install jupyter extensions
RUN mkdir -p -m 700 ./.jupyter/ && \
    echo "c.NotebookApp.ip = '*'" >> ./.jupyter/jupyter_notebook_config.py

RUN git clone https://github.com/ipython-contrib/IPython-notebook-extensions.git

RUN mkdir -p .local/share/jupyter

RUN cd IPython-notebook-extensions && $HOME/anaconda3/bin/python setup.py install

# Enable some of the extensions
RUN ./anaconda3/bin/jupyter nbextension enable usability/autosavetime/main && \
    ./anaconda3/bin/jupyter nbextension enable usability/chrome-clipboard/main && \
    ./anaconda3/bin/jupyter nbextension enable usability/dragdrop/main && \
    ./anaconda3/bin/jupyter nbextension enable usability/rubberband/main && \
    ./anaconda3/bin/jupyter nbextension enable usability/highlighter/highlighter && \
    ./anaconda3/bin/jupyter nbextension enable usability/runtools/main && \
    ./anaconda3/bin/jupyter nbextension enable config/config_menu/main && \
    ./anaconda3/bin/jupyter nbextension enable usability/codefolding/main && \
    ./anaconda3/bin/jupyter nbextension enable codemirrormode/skill/skill && \
    ./anaconda3/bin/jupyter nbextension enable usability/search-replace/main && \
    ./anaconda3/bin/jupyter nbextension enable usability/toc2/main && \
    ./anaconda3/bin/jupyter nbextension enable usability/spellchecker/main && \
    ./anaconda3/bin/jupyter nbextension enable usability/tree-filter/main && \
    ./anaconda3/bin/jupyter nbextension enable styling/table_beautifier/main

# remove trash
RUN rm Anaconda3-4.0.0-Linux-x86_64.sh

# make the folder that will be the notebook root
RUN mkdir notebooks

WORKDIR /home/deploy/notebooks

EXPOSE 8888

CMD ../anaconda3/bin/jupyter notebook