DOCKER_IMAGE_VERSION=8-jdk
DOCKER_IMAGE_NAME=artem236/rpi-openjdk
DOCKER_IMAGE_TAGNAME=$(DOCKER_IMAGE_NAME):$(DOCKER_IMAGE_VERSION)

default: build

build:
	docker build -t $(DOCKER_IMAGE_TAGNAME) .
	docker tag $(DOCKER_IMAGE_TAGNAME) $(DOCKER_IMAGE_NAME):8u131-jdk
	docker tag $(DOCKER_IMAGE_TAGNAME) $(DOCKER_IMAGE_NAME):jdk
	docker tag $(DOCKER_IMAGE_TAGNAME) $(DOCKER_IMAGE_NAME):latest

push:
	docker push $(DOCKER_IMAGE_TAGNAME) 
	docker push $(DOCKER_IMAGE_NAME):8u131-jdk
	docker push $(DOCKER_IMAGE_NAME):jdk
	docker push $(DOCKER_IMAGE_NAME):latest

test:
	docker run --rm $(DOCKER_IMAGE_TAGNAME) /bin/echo "Success."

rmi:
	docker rmi -f $(DOCKER_IMAGE_TAGNAME)

rebuild: rmi build