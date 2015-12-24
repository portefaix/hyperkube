# VERSION 1.1.3
# AUTHOR:         Nicolas Lamirault <nicolas.lamirault@gmail.com>
# DESCRIPTION:    portefaix/grafana

FROM portefaix/base:3.2
MAINTAINER Nicolas Lamirault <nicolas.lamirault@gmail.com>

ENV KUBERNETES_VERSION 1.1.3
ENV GOPATH /go

RUN apk add --update build-base curl ca-certificates go git mercurial openssl iptables


# Install glibc
RUN cd /tmp && \
    wget "https://circle-artifacts.com/gh/andyshinn/alpine-pkg-glibc/6/artifacts/0/home/ubuntu/alpine-pkg-glibc/packages/x86_64/glibc-2.21-r2.apk" && \
    apk add --allow-untrusted glibc-2.21-r2.apk && \
    wget "https://circle-artifacts.com/gh/andyshinn/alpine-pkg-glibc/6/artifacts/0/home/ubuntu/alpine-pkg-glibc/packages/x86_64/glibc-bin-2.21-r2.apk" && \
    apk add --allow-untrusted glibc-bin-2.21-r2.apk && \
    /usr/glibc/usr/bin/ldconfig /lib /usr/glibc/usr/lib

# Install Kubernetes
RUN curl -LO https://github.com/kubernetes/kubernetes/releases/download/v${KUBERNETES_VERSION}/kubernetes.tar.gz && \
    mkdir /srv/ && \
    tar zxvf kubernetes.tar.gz -C / && \
    tar zxvf /kubernetes/server/kubernetes-server-linux-amd64.tar.gz && \
    cp /kubernetes/server/bin/* /srv/ && \
    rm -rf /go /tmp/* /var/cache/apk/* /root/.n* /kubernetes && \
    mv /srv/* /

RUN mkdir -p /etc/kubernetes/manifests
COPY master.json /etc/kubernetes/manifests/master.json
COPY master-multi.json /etc/kubernetes/manifests/master-multi.json
COPY namespace.yaml /etc/kubernetes/

# ENTRYPOINT ["/usr/local/bin/hyperkube"]

CMD ["/hyperkube", "--help"]
