SHELL       := /bin/sh
IMAGE       := django
REPOSITORY  := psmwareltd
VERSION     := 3.2.3

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