PROJECT ?= k8s-testimages
IMG = gcr.io/$(PROJECT)/perf-tests-util/containerd
TAG = v0.0.1

all: push

build: Dockerfile
	docker build --pull -t $(IMG):$(TAG) .
	docker tag $(IMG):$(TAG) $(IMG):latest
	@echo Built $(IMG):$(TAG) and tagged with latest

.PHONY: push
push: build
	docker push $(IMG):$(TAG)
	docker push $(IMG):latest
	@echo Pushed $(IMG) with :latest and :$(TAG) tags
