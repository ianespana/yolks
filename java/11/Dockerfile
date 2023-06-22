FROM        --platform=$TARGETOS/$TARGETARCH eclipse-temurin:11.0.13_8-jdk-focal

LABEL       author="Michael Parker | Ian Ramirez" maintainer="parker@pterodactyl.io"

LABEL       org.opencontainers.image.source="https://github.com/ianespana/yolks"
LABEL       org.opencontainers.image.licenses=MIT

RUN         apt update -y \
						&& apt install -y curl lsof ca-certificates openssl git tar sqlite3 fontconfig tzdata iproute2 libfreetype6 graphviz \
						&& useradd -d /home/container -m container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
