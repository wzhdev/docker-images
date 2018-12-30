FROM alpine:3.8

COPY ca.crt /usr/local/share/ca-certificates/ca.crt

RUN \
    echo "http://mirrors.aliyun.com/alpine/v3.8/main" > /etc/apk/repositories && \
    echo "http://mirrors.aliyun.com/alpine/v3.8/community" >> /etc/apk/repositories  && \
    apk update upgrade && \
	apk add --no-cache ca-certificates && \
	update-ca-certificates && rm -f /usr/local/share/ca-certificates/ca.crt
    ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo "Asia/Shanghai" > /etc/timezone