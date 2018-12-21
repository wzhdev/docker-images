FROM wzhdev/alpine:3.8-bash

COPY ca.crt /usr/local/share/ca-certificates/ca.crt

RUN \
    apk add --no-cache ca-certificates git && \
	update-ca-certificates && rm -f /usr/local/share/ca-certificates/ca.crt
	
