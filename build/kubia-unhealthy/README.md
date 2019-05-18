To build:

# prepare qemu
- docker run --rm --privileged multiarch/qemu-user-static:register --reset
# build image
- docker build -t adegiuli/kubia-unhealthy:tag 
