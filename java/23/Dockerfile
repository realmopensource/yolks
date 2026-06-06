FROM        --platform=$TARGETOS/$TARGETARCH eclipse-temurin:23-jdk-noble

LABEL       author="Realm" maintainer="support@realmctl.com"

LABEL       org.opencontainers.image.source="https://github.com/realmopensource/yolks"
LABEL       org.opencontainers.image.licenses=MIT

# hadolint ignore=DL3015
RUN         apt-get update -y \
            && apt-get upgrade -y \
            && apt-get install -y \
                curl \
                lsof \
                ca-certificates \
                openssl \
                git \
                tar \
                sqlite3 \
                fontconfig \
                libfreetype6 \
                tzdata \
                iproute2 \
                libstdc++6 \
                zip \
                unzip \
            && rm -rf /var/lib/apt/lists/* \
            && useradd -d /home/container -m container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
