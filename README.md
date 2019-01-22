# blue-prom-test-go
Demo code in go to show prometheus statistics

# Build go container

```
# statically linked
docker run --rm -v "$PWD":/usr/src/demo -w /usr/src/demo golang:1.10 bash -c 'go get ./... ; CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -v'
docker build -t demo-go -f Docker-go ./
docker run -it --rm --name demo-go -p 8080:8080 demo-go
```

# Install consul service

```
cp demo-go.json /opt/consul/config/
```
