FROM jupyter/notebook

# install some useful extensions
RUN pip3 install https://github.com/ipython-contrib/IPython-notebook-extensions/archive/master.zip

# enable the extensions previously installed
RUN jupyter nbextension enable usability/autosavetime/main && \
	jupyter nbextension enable usability/chrome-clipboard/main && \
    jupyter nbextension enable usability/dragdrop/main && \
    jupyter nbextension enable usability/rubberband/main && \
    jupyter nbextension enable usability/highlighter/highlighter && \
    jupyter nbextension enable usability/runtools/main && \
    jupyter nbextension enable config/config_menu/main && \
    jupyter nbextension enable usability/codefolding/main && \
    jupyter nbextension enable codemirrormode/skill/skill && \
    jupyter nbextension enable usability/search-replace/main && \
    jupyter nbextension enable usability/toc2/main

# start the server
CMD ["jupyter", "notebook"]
