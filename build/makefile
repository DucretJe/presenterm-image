# Version of presenterm
VERSION := v0.6.1

# Define the image name
IMAGE_NAME := presenterm-image

# Define the path to the Dockerfile
DOCKERFILE_PATH := ../docker

.PHONY: build test push

# Default target
all: build test

# Build the Docker image
build:
	@docker buildx create --name multiarchbuilder --use && \
	docker buildx build --load -t $(IMAGE_NAME):$(VERSION) $(DOCKERFILE_PATH) && \
	docker buildx rm multiarchbuilder

# Test the Docker image
test: build
	@{ \
	docker run --rm $(IMAGE_NAME):$(VERSION) --help; \
	EXIT_CODE=$$?; \
	if [ $$EXIT_CODE -eq 0 ]; then \
		echo "\033[0;32mSuccess: The command executed successfully.\033[0m"; \
	else \
		echo "\033[0;31mError: The command failed with exit code $$EXIT_CODE.\033[0m"; \
		exit 1; \
	fi; \
	}


# Push the Docker image
push:
	@docker buildx create --name multiarchbuilder --use && \
	docker buildx build --platform linux/amd64,linux/arm64 -t ghcr.io/ducretje/$(IMAGE_NAME):$(VERSION) $(DOCKERFILE_PATH) --push
	@docker buildx rm multiarchbuilder
