IMAGE_NAME=seldonio/sk-example-mnist
IMAGE_VERSION=0.3

train:
	python train.py

build_image:
	s2i build -E environment_rest . seldonio/seldon-core-s2i-python3:1.4.0-dev ${IMAGE_NAME}:${IMAGE_VERSION}

push_image:
	docker push $(IMAGE_NAME):$(IMAGE_VERSION)

kind_load:
	kind load -v 3 docker-image ${IMAGE_NAME}:${IMAGE_VERSION}


clean:
	rm -f sk.pkl
	rm -rf MNIST_data
