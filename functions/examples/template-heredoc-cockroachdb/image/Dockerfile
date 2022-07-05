# Copyright 2019 The Kubernetes Authors.
# SPDX-License-Identifier: Apache-2.0

FROM golang:1.18-stretch
ENV CGO_ENABLED=0
RUN GOPROXY=https://goproxy.cn,direct go install sigs.k8s.io/kustomize/kustomize/v4@latest

FROM alpine:latest
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories && apk add --no-cache bash
COPY --from=0 /go/bin/kustomize /usr/local/bin
COPY cockroachdb-template.sh /usr/local/bin/config-function
CMD ["config-function"]
