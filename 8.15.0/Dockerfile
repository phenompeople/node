FROM amazonlinux:2
LABEL maintainer="rajesh.jonnalagadda@phenompeople.com" \
      version="8.15.0"
RUN yum install -q -y  wget shadow-utils tar gzip xz fontconfig&& \
    useradd -d  /opt/phenom phenom -u 1004 && \
    mkdir -p /opt/phenom/scripts
ARG NODE_VERSION=v8.15.0
ENV NODE_VERSION=${NODE_VERSION}
RUN wget -q -O /tmp/node.tar.xz http://nodejs.org/dist/${NODE_VERSION}/node-${NODE_VERSION}-linux-x64.tar.xz && \
	tar -xJf /tmp/node.tar.xz -C /usr/local && \
	ln -sf /usr/local/node-${NODE_VERSION}-linux-x64 /usr/local/node && \
	rm -rf /tmp/node.tar.xz
ENV PATH=/usr/local/node/bin:$PATH
ENTRYPOINT ["node"]