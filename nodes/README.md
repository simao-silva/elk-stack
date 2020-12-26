# Filebeat on ARM64 

### Build image
```shell
docker build -t filebeat-arm64 -f Dockerfile.arm64 .
```

### How to run
```shell
docker run -it -v /var/log/auth.log:/var/log/auth.log filebeat-arm64:latest 
```
