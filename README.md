# default_docker

The idea is to user the `.docker/` folder to contain all the docker setup, while the app is going to reside in the root.

I have created the file `docker.sh` to simplify the management of the image.

```
sudo ./docker.sh build
sudo ./docker.sh rebuild
sudo ./docker.sh start
sudo ./docker.sh stop
sudo ./docker.sh run
```