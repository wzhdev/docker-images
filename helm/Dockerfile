FROM wzhdev/alpine

COPY ca.crt /usr/local/share/ca-certificates/ca.crt

RUN apk add --no-cache ca-certificates && update-ca-certificates && \
	rm -f /usr/local/share/ca-certificates/ca.crt

ENV KUBECONFIG=/etc/kube.conf

COPY config /etc/kube.conf
COPY helm /usr/bin/helm
COPY kubectl /usr/bin/kubectl

RUN helm init --skip-refresh --client-only && helm repo remove stable && \
	helm plugin install https://github.com/chartmuseum/helm-push && \
	helm repo add --password 123456 --username admin wzhdev https://harbor.wzh/chartrepo/wzhdev

CMD bash