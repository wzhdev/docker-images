FROM alpine

ENV KUBE_LATEST_VERSION="v1.13.0"
ENV HELM_VERSION="v2.12.0"

ENV KUBECONFIG=/etc/kube.conf

RUN apk add --no-cache ca-certificates bash git

COPY config /etc/kube.conf
COPY helm /usr/bin/helm
COPY kubectl /usr/bin/kubectl

CMD bash