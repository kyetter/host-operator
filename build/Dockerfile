FROM registry.access.redhat.com/ubi8/ubi-minimal:latest

LABEL maintainer "KubeSaw <devsandbox@redhat.com>"
LABEL author "KubeSaw <devsandbox@redhat.com>"

ENV OPERATOR=/usr/local/bin/host-operator \
    USER_UID=1001 \
    USER_NAME=host-operator \
    LANG=en_US.utf8

# install operator binary
COPY build/_output/bin/host-operator ${OPERATOR}

COPY build/bin /usr/local/bin
RUN  /usr/local/bin/user_setup

ENTRYPOINT ["/usr/local/bin/entrypoint"]

USER ${USER_UID}
