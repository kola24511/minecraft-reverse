SERVICE_NAME=app
DOMAIN=localhost
DC=$(if $(shell docker-compose --version 2>/dev/null),docker-compose,docker compose) -f traefik/docker-compose.yml

CERT_DIR=.certs
CERT_FILE=$(CERT_DIR)/traefik-selfsigned.crt
KEY_FILE=$(CERT_DIR)/traefik-selfsigned.key

.DEFAULT_GOAL := up
.PHONY:

all: certs run

in:
	${DC} exec ${SERVICE_NAME} sh

###> DOCKER COMPOSE
start:
	${DC} start
stop:
	${DC} stop
up:
	${DC} up -d
build:
	${DC} build
down:
	${DC} down
###< DOCKER COMPOSE

###> certs
certs:
	mkdir -p $(CERT_DIR)
	openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
		-keyout $(KEY_FILE) -out $(CERT_FILE) \
		-subj "/CN=$(DOMAIN)"
###< certs