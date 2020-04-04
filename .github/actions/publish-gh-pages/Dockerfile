FROM ubuntu:bionic

LABEL "name"="Publish k8s.camp"
LABEL "maintainer"="Paul Czarkowski"
LABEL "version"="0.0.1"

LABEL "com.github.actions.name"="Publish hugo to gh-pages"
LABEL "com.github.actions.description"="Publish hugo to gh-pages"
LABEL "com.github.actions.icon"="package"
LABEL "com.github.actions.color"="green"

RUN apt-get update > /dev/null && apt-get -yqq install curl git > /dev/null

RUN curl -sSL \
    https://github.com/gohugoio/hugo/releases/download/v0.68.3/hugo_extended_0.68.3_Linux-64bit.tar.gz | \
    tar xzf - hugo && \
    chmod +x /hugo && \
    /hugo version

COPY entrypoint.sh /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]