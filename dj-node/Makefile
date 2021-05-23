SHELL       := /bin/sh
IMAGE       := dj-node
REPOSITORY  := psmwareltd
VERSION     := 1.0

### Executables
DOCKER := docker

### Docker Targets

.PHONY: build
build:
	$(DOCKER) build -t $(REPOSITORY)/$(IMAGE):$(VERSION) --no-cache --rm .
	$(DOCKER) tag $(REPOSITORY)/$(IMAGE):$(VERSION) $(REPOSITORY)/$(IMAGE):latest

.PHONY: push
push:
	$(DOCKER) push $(REPOSITORY)/$(IMAGE):$(VERSION)
	$(DOCKER) push $(REPOSITORY)/$(IMAGE):latest