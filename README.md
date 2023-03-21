## 👋 Welcome to supabase 🚀  

supabase README  
  
  
## Requires scripts to be installed  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 systemmgr --config && systemmgr install scripts  
```

## Automatic install/update  

```shell
dockermgr update supabase
```

OR

```shell
mkdir -p "$HOME/.local/share/srv/docker/supabase/dataDir"
git clone "https://github.com/dockermgr/supabase" "$HOME/.local/share/CasjaysDev/dockermgr/supabase"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/supabase/dataDir/." "$HOME/.local/share/srv/docker/supabase/dataDir/"
```

## via command line  

```shell
docker pull casjaysdevdocker/supabase:latest && \
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-supabase \
--hostname casjaysdev-supabase \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/srv/docker/supabase/dataDir/data:/data:z \
-v $HOME/.local/share/srv/docker/supabase/dataDir/config:/config:z \
-p 80:80 \
casjaysdevdocker/supabase:latest
```

## via docker-compose  

```yaml
version: "2"
services:
  supabase:
    image: casjaysdevdocker/supabase
    container_name: supabase
    environment:
      - TZ=America/New_York
      - HOSTNAME=casjaysdev-supabase
    volumes:
      - $HOME/.local/share/srv/docker/supabase/dataDir/data:/data:z
      - $HOME/.local/share/srv/docker/supabase/dataDir/config:/config:z
    ports:
      - 80:80
    restart: always
```

## Author  

📽 dockermgr: [Github](https://github.com/dockermgr) 📽  
🤖 casjay: [Github](https://github.com/casjay) [Docker](https://hub.docker.com/r/casjay) 🤖  
⛵ CasjaysDevDocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/r/casjaysdevdocker) ⛵  
