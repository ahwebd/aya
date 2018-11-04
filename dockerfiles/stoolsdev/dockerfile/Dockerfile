FROM ahwebd/stools

USER root

# replace shell with bash
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# Nodejs
# check polymer-cli requirements for nodejs version
# https://www.polymer-project.org/3.0/docs/tools/polymer-cli#install
# https://www.polymer-project.org/3.0/docs/tools/node-support

# Environment variables

# https://github.com/creationix/nvm/releases
ENV NVM_VERSION v0.33.11

# https://www.polymer-project.org/3.0/docs/tools/node-support
# https://nodejs.org/en/download/
ENV NODE_VERSION 10.13.0

ENV NVM_DIR /usr/local/nvm

# install nvm
# https://github.com/creationix/nvm#install-script
RUN set -ex \
    && mkdir $NVM_DIR \
    && curl -o- https://raw.githubusercontent.com/creationix/nvm/$NVM_VERSION/install.sh | bash

# install node and npm
RUN set -ex \
    && source $NVM_DIR/nvm.sh \
    && nvm install $NODE_VERSION \
    && nvm alias default $NODE_VERSION \
    && nvm use default

# add node and npm to path so the commands are available
ENV NODE_PATH $NVM_DIR/v$NODE_VERSION/lib/node_modules
ENV PATH $NVM_DIR/versions/node/v$NODE_VERSION/bin:$PATH

# confirm installation
RUN node -v
RUN npm -v

# npm, polymer-cli
RUN set -ex \
    && npm install npm@latest -g \
    && npm install -g polymer-cli --unsafe-perm \
    && polymer --version

USER dkr
