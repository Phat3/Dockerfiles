# Collection of Dockerfile

## Debian stack
I used debian as base for all my other application following thhis schema:

- **Debian custom** : provides a common layer where the most common utility are installed

- **Python stack** : provides a layer where all the python environment is installed along with utilities such as pip 

- **Node stack** : provides a layer where all the node environment is installed along with the most common utilities such as npm and bower 

- **Chrisper** : images containing the application [Chrisper](https://github.com/invernizzi/Chrisper)

## Jupyter Notebooks
Images that builds my [Jupyter Notebook](https://hub.docker.com/r/phate/jupyter_notebook_custom/) environment installing and activating my favorites extensions.

## Kali linux
A kali linux images customized with the tool I use the most.


## Realms-wiki-dev
Images that creates an environment setup to test and develop a custom version of [Realms-wiki](https://github.com/scragg0x/realms-wiki)