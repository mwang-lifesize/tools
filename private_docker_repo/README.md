# docker private repo 

## client 
How to setup to use your docker to use this self-signed docker registry

### For Linux user:

(1) add /etc/hosts

10.10.20.149 docker-eng.lifesize.com

(3) download the cert file

sudo mkdir -p /etc/docker/certs.d/docker-eng.lifesize.com/

sudo wget  https://raw.githubusercontent.com/mwang-lifesize/tools/master/private_docker_repo/certs/docker-eng.crt -O /etc/docker/certs.d/docker-eng.lifesize.com/ca.rt


### For mac or window user

   see : https://docs.docker.com/registry/insecure/#use-self-signed-certificates

### sample use as End-user 

docker pull docker-eng.lifesize.com/lifesize.sky.me_build.ubuntu_12.04:latest

docker_run docker-eng.lifesize.com/lifesize.sky.me_build.ubuntu_12.04:latest ./build.py -j8
 
Get a list of repo: https://docker-eng.lifesize.com/v2/_catalog
 
### For Developer:

#### how to upload a docker image
build a local docker image, and tag it, and push to registra

e.g:

docker tag lifesize.sky.me_build.ubuntu_12.04 docker-eng.lifesize.com/lifesize.sky.me_build.ubuntu_12.04

docker push docker-eng.lifesize.com/lifesize.sky.me_build.ubuntu_12.04
 

