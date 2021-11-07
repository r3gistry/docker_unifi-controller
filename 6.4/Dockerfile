FROM openjdk:8-jre-alpine3.9

LABEL maintainer="R3GISTRY"
LABEL description="UniFi-Network in Docker."

WORKDIR /tmp/

ADD \
https://dl.ui.com/unifi/6.4.54/UniFi.unix.zip \
.

RUN \
apk add --no-cache unzip \
&& unzip UniFi.unix.zip \
&& mkdir /usr/local/unifi-network/ \
&& mv UniFi/* /usr/local/unifi-network/ \
&& ln -s /mnt/unifi-network/data/ /usr/local/unifi-network/data \
&& ln -s /mnt/unifi-network/logs/ /usr/local/unifi-network/logs \
&& ln -s /mnt/unifi-network/cert/ /usr/local/unifi-network/cert \
&& ln -s /mnt/unifi-network/run/ /usr/local/unifi-network/run \
&& echo -e "db.mongo.local=false\n\
db.mongo.uri=mongodb\://mongodb\:27017/unifi-network\n\
statdb.mongo.uri=mongodb\://mongodb\:27017/unifi-network_stat\n\
unifi.db.name=unifi\n" > /mnt/unifi-network/data/system.properties \
&& rm -r * \
&& apk del unzip

VOLUME ["/mnt/unifi-network/data/", "/mnt/unifi-network/logs", "/mnt/unifi-network/cert/", "/mnt/unifi-network/run/"]

ENTRYPOINT ["java", "-XX:+UnlockExperimentalVMOptions", "-XX:+UseCGroupMemoryLimitForHeap", "-jar", "/usr/local/unifi-network/lib/ace.jar"]
CMD ["help"]
