.PHONY: help

help:
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'

build:  ## Build docker images
	docker-compose build

npm:  ## Install dependencies
	docker-compose run app npm install

lint:
	docker-compose run app npm run lint

clean:  ## Remove all images and volumes
	docker-compose down --rmi all --volumes

setup: build npm  ## Setup current project
