FROM openjdk:8-jre-slim-buster

LABEL maintainer="R3GISTRY"
LABEL description="UniFi-Network in Docker."

WORKDIR /tmp/

ADD \
https://dl.ui.com/unifi/6.2.26/UniFi.unix.zip \
.

RUN \
apt-get update \
&& apt-get -y --no-install-recommends install unzip \
&& rm -rf /var/lib/apt/lists/* \
&& unzip UniFi.unix.zip \
&& mkdir /usr/local/unifi-network/ \
&& mv UniFi/* /usr/local/unifi-network/ \
&& ln -s /mnt/unifi-network/data/ /usr/local/unifi-network/data \
&& ln -s /mnt/unifi-network/logs/ /usr/local/unifi-network/logs \
&& ln -s /mnt/unifi-network/cert/ /usr/local/unifi-network/cert \
&& rm -r * \
&& apt-get -y --auto-remove purge unzip

VOLUME ["/mnt/unifi-network/data/", "/mnt/unifi-network/logs/", "/mnt/unifi-network/cert/"]

ENTRYPOINT ["java", "-XX:+UnlockExperimentalVMOptions", "-XX:+UseCGroupMemoryLimitForHeap", "-jar", "/usr/local/unifi-network/lib/ace.jar"]
CMD ["help"]
