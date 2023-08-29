- [Heart Thymes](https://twitch.tv/heartthymes) learning path

## How to docker   

```bash
sudo docker pull ubuntu:latest

sudo mkdir -p ~/Projects/docker-storage

sudo docker run -ti -v ~/Projects/docker-storage:/htdata htubuntu /bin/bash

docker ps

sudo docker commit -p container_id htubuntu
```

## You don't need a docker if you share the repo with another account
