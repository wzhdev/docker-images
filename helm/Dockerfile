FROM alpine

RUN \
    echo "http://mirrors.aliyun.com/alpine/v3.8/main" > /etc/apk/repositories && \
    echo "http://mirrors.aliyun.com/alpine/v3.8/community" >> /etc/apk/repositories  && \
    apk update upgrade && \
    apk add --no-cache procps curl bash ca-certificates git && \
    ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo "Asia/Shanghai" > /etc/timezone


ENV KUBE_LATEST_VERSION="v1.13.0"
ENV HELM_VERSION="v2.12.0"

ENV KUBECONFIG=/etc/kube.conf

COPY config /etc/kube.conf
COPY helm /usr/bin/helm
COPY kubectl /usr/bin/kubectl

CMD bash