# docker-openfalcon-transfer

## Build

Enter the following command in the repo directory.

```
$sudo docker build --force-rm=true -t openfalcon-graph .
```

## Run

### Basic Run

Use default configuration, and falcon-transfer package.

```
$sudo docker run -dti --name transfer -p 6060:6060 -p 8443:8443 -p 4444:4444 openfalcon-transfer
```

### Advanced Run

+ Self-defined configuration

  Replace file **cfg.json** in the volume */config*.  
  For more detail about **cfg.json**, see [Transfer](http://book.open-falcon.com/zh/install/transfer.html).

+ New falcon-transfer package

  Replace file **falcon-transfer.tar.gz** in the volume */package*.
  
  For example, **cfg.json** in /tmp/config and **falcon-transfer.tar.gz** in /tmp/pack,

```
$sudo docker run -dti --name transfer -v /tmp/pack:/package -v /tmp/config/cfg.json:/config/cfg.json -p 6060:6060 -p 8443:8443 -p 4444:4444 openfalcon-transfer
```
