IMAGE_NAME="param:2.3.splmc"

create:
	docker build --no-cache -t ${IMAGE_NAME} .

rebuild:
	make rmi
	make create

rmi:
	docker rmi ${IMAGE_NAME}
