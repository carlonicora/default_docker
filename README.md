# setup

The idea is that this project is the repository for an application (in this case a php CLI app). The application will reside in the root or the project, while the `.docker/` folder to contain all the docker setup files.


# Shell

I have created the file `docker.sh` to simplify the management of the image.

```
sudo ./docker.sh build
sudo ./docker.sh rebuild
sudo ./docker.sh start
sudo ./docker.sh stop
sudo ./docker.sh run
```