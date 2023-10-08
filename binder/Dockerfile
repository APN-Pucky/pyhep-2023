FROM apnpucky/ubuntu-python-latexmk:20221205092215
RUN apt-get install gfortran
RUN echo "Install FORM"
RUN wget https://github.com/vermaseren/form/releases/download/v4.3.1/form-4.3.1-x86_64-linux.tar.gz
RUN tar -xzf form-4.3.1-x86_64-linux.tar.gz


RUN echo "Install qgraf"
RUN mkdir qgraf
RUN cd qgraf && wget http://anonymous:anonymous@qgraf.tecnico.ulisboa.pt/v3.6/qgraf-3.6.6.tgz && tar -xzf qgraf-3.6.6.tgz && gfortran -o qgraf qgraf-3.6.6.f08 

ENV PATH=$PATH:$PWD/form-4.3.1-x86_64-linux/
ENV PATH=$PATH:$PWD/qgraf/


RUN python3 -m pip install --no-cache-dir notebook jupyterlab
RUN pip install --no-cache-dir jupyterhub

ARG NB_USER=jovyan
ARG NB_UID=1000
ENV USER ${NB_USER}
ENV NB_UID ${NB_UID}
ENV HOME /home/${NB_USER}

RUN adduser --disabled-password \
    --gecos "Default user" \
    --uid ${NB_UID} \
    ${NB_USER}

# Make sure the contents of our repo are in ${HOME}
COPY . ${HOME}
USER root
RUN chown -R ${NB_UID} ${HOME}
WORKDIR ${HOME}
USER ${NB_USER}
RUN pip install --no-cache-dir -r ${HOME}/requirements.txt