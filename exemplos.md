# Exemplos

* Dockerfile
    * Correto
        * `docker image build -t correto:share .`
    * Errado
        * `docker image build -t errado:share .`

* Containers
    * Efêmero
        * `docker image build -t efemero:share .`
        * `docker container run -d -p 9091:9090 -e HTTP_PORT=9090 --name efemero efemero:share`
    * Zumbi
        * `docker image build -t zumbi:share .`
        * `docker container run -d -p 9092:9090 -dit --restart=always -e HTTP_PORT=9090 --name zumbi zumbi:share`

* Docker-compose
    * APP Vote
        * `docker-compose up -d`
    * App simples
        * `docker-compose up -d`

* Desktop
    * VSCODE
        *`docker run -d \
            -v /tmp/.X11-unix:/tmp/.X11-unix \
            -e DISPLAY=unix$DISPLAY \
            --device /dev/dri \
            --name vscode \
            --net host \
            --hostname $(hostname) \
            -e UID=$(id -u) \
            -e GID=$(id -g) \
            -e USERNAME=$(id -un) \
            tegieng7/vscode-python`