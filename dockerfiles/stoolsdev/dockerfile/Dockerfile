FROM ahwebd/stools

USER root

# Nodejs
# check polymer-cli requirements for nodejs version
# https://www.polymer-project.org/3.0/docs/tools/polymer-cli#install
# https://www.polymer-project.org/3.0/docs/tools/node-support
# https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions
RUN set -ex \
    && curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash - \
    && apt-get install -y nodejs \
    && rm -rf /var/lib/apt/lists/*

# npm, bower, polymer-cli
RUN set -ex \
    && npm install npm@latest -g \
    && npm install -g polymer-cli

USER dkr
