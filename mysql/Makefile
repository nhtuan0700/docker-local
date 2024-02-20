include .env

DKC=docker compose 
# RUN_CONTAINER=docker compose exec mysql bash
RUN_CONTAINER=docker exec -it ${CONTAINER_NAME} bash

mysql-up:
	${DKC} up -d

mysql-down:
	${DKC} down -d

mysql-bash:
	$(RUN_CONTAINER)
