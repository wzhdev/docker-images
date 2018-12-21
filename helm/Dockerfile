FROM wzhdev/git

ENV KUBECONFIG=/etc/kube.conf

COPY config /etc/kube.conf
COPY helm /usr/bin/helm
COPY kubectl /usr/bin/kubectl

RUN helm init --skip-refresh --client-only && helm repo remove stable && \
	helm plugin install https://github.com/chartmuseum/helm-push

CMD bash
