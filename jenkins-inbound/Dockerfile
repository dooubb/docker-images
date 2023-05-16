FROM jenkins/inbound-agent:latest-jdk11
USER 0
RUN curl -fsSL https://get.docker.com | sh 

RUN	curl -L "https://github.com/sigstore/cosign/releases/download/v1.13.0/cosign-linux-amd64"  -o /usr/bin/cosign \
	&& curl -L "https://github.com/docker/compose/releases/download/v2.17.3/docker-compose-linux-x86_64" -o /usr/local/lib/docker/cli-plugins/docker-compose \
    && curl -L "https://dl.k8s.io/release/v1.26.0/bin/linux/amd64/kubectl" -o /usr/bin/kubectl \
    && curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-Linux-x86_64"  -o /usr/bin/docker-compose \
    && curl -L "https://github.com/kubernetes-sigs/kustomize/releases/download/kustomize%2Fv5.0.0/kustomize_v5.0.0_linux_amd64.tar.gz" -o /tmp/kustomize_v5.0.0_linux_amd64.tar.gz \
    && tar -zxvf /tmp/kustomize_v5.0.0_linux_amd64.tar.gz -C /usr/bin/ \
    && chmod +x /usr/bin/docker-compose \
    && chmod +x /usr/bin/kustomize \
    && chmod +x /usr/bin/kubectl \
    && chmod +x /usr/bin/cosign \
    && chmod +x /usr/local/lib/docker/cli-plugins/docker-compose \
    && rm -rf /tmp
USER jenkins
