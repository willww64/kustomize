# Copyright 2019 The Kubernetes Authors.
# SPDX-License-Identifier: Apache-2.0

include ../Makefile-examples-base.mk

.PHONY: image
image:
	docker build image -t willww64/kustomize-functions-example-nginx:v0.2.0
	docker push willww64/kustomize-functions-example-nginx:v0.2.0
