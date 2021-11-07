## UniFi-Network

### What is it?

UniFi-Network is contributed by [Ubiquiti](https://www.ui.com/download-software/).

Due to licensing, no one can redistribute the software. Please build this image in your environment.

### Example usages

- To build the image:

```console
$ docker build YOUR_VERSION/ --tag r3gistry/unifi-network:YOUR_VERSION
```

- To run with Compose after updating `docker-compose.yml`:

```console
$ docker-compose up
```

After first run, stop containers, add the following lines and make changes to `system.properties` at `unifi-network_data`:

```
db.mongo.local=false
db.mongo.uri=mongodb://mongodb:27017/unifi-network
statdb.mongo.uri=mongodb://mongodb:27017/unifi-network_stat
unifi.db.name=unifi
```

- To fetch logs of a container:

```console
$ docker logs YOUR_CONTAINER_NAME
```

### Donations

If you like to buy us coffee, you can donate to here:

- [Ko-fi](https://ko-fi.com/calvintam236)
- BTC: `1MTkPFtp3qxE4Y98pTHP3z767RGKmrT92a`
- ETH: `0x5896a85E8c175c563DC00087535582394d394838`
- XMR: `474adYsC8sLVM5gK8DbvtUVb237y9m5eMeRuYpJJVuoYUuMN5EYDuixHWxpEr6iNBb2zv3gowmJjcRoTrjhJLvMTRD1eKio`
- ETC: `0xFaBA3be3b3De5469C3F6C6185150928F3773C7b4`
- ZEC: `t1Z5Kc75JQ17txyaDUfwwyabTgsJMfuuSp4`
