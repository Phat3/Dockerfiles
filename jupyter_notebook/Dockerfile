FROM debian_custom

# Install dependencies for anaconda
RUN apt-get install -y bzip2

# Install everythin as an unprivilege user
RUN useradd -m -s /bin/bash deploy

USER deploy

WORKDIR /home/deploy/

# Download the latest version of anaconda
RUN wget http://repo.continuum.io/archive/Anaconda3-4.1.1-Linux-x86_64.sh

# Install anaconda
RUN bash Anaconda3-4.1.1-Linux-x86_64.sh -b

## Install jupyter extensions
RUN mkdir -p -m 700 ./.jupyter/ && \
   echo "c.NotebookApp.ip = '*'" >> ./.jupyter/jupyter_notebook_config.py

RUN ./anaconda3/bin/conda install -c conda-forge jupyter_contrib_nbextensions -y

# Enable some of the extensions
RUN ./anaconda3/bin/jupyter nbextension enable autosavetime/main && \
    ./anaconda3/bin/jupyter nbextension enable chrome-clipboard/main && \
    ./anaconda3/bin/jupyter nbextension enable dragdrop/main && \
    ./anaconda3/bin/jupyter nbextension enable rubberband/main && \
    ./anaconda3/bin/jupyter nbextension enable highlighter/highlighter && \
    ./anaconda3/bin/jupyter nbextension enable runtools/main && \
    ./anaconda3/bin/jupyter nbextension enable codefolding/main && \
    ./anaconda3/bin/jupyter nbextension enable search-replace/main && \
    ./anaconda3/bin/jupyter nbextension enable toc2/main && \
    ./anaconda3/bin/jupyter nbextension enable spellchecker/main && \
    ./anaconda3/bin/jupyter nbextension enable table_beautifier/main &&\
    ./anaconda3/bin/jupyter nbextension enable scratchpad/main &&\
    ./anaconda3/bin/jupyter nbextension enable tree-filter/index &&\
    ./anaconda3/bin/jupyter nbextension enable move_selected_cells/main &&\
#    ./anaconda3/bin/jupyter nbextension enable code_prettify/main

# remove trash
RUN rm Anaconda3-4.1.1-Linux-x86_64.sh

# make the folder that will be the notebook root
RUN mkdir notebooks

WORKDIR /home/deploy/notebooks

EXPOSE 8888

CMD ../anaconda3/bin/jupyter notebook
