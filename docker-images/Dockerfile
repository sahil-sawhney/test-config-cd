FROM alpine:3.12

ENV KUBECTL_VERSION="v1.18.3"
ENV HELM_VERSION="v3.2.3"

RUN apk add --no-cache bash curl

RUN curl -LO https://storage.googleapis.com/kubernetes-release/release/${KUBECTL_VERSION}/bin/linux/amd64/kubectl && \
    mv ./kubectl /usr/local/bin/kubectl && \
    chmod +x /usr/local/bin/kubectl && \
    mkdir -p /root/.kube

RUN curl -LO https://get.helm.sh/helm-${HELM_VERSION}-linux-amd64.tar.gz && \
    tar -zxvf helm-${HELM_VERSION}-linux-amd64.tar.gz && \
    mv linux-amd64/helm /usr/local/bin/helm && \
    chmod +x /usr/local/bin/helm

RUN curl -s https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh | bash && \
    mv ./kustomize /usr/local/bin/kustomize && \
    chmod +x /usr/local/bin/kustomize

CMD [ "bash" ]
