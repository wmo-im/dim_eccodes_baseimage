# eccodes-docker
for builder the eccodes docker base image used in various wmo software projects

### build new release
docker build -t eccodes:x.y.z . # note sha

### push image in GHCR
docker tag $SHA ghcr.io/wmo-im/eccodes:x.y.z
docker image push ghcr.io/wmo-im/eccodes:x.y.z

### push image wmoim docker-hub
docker tag $SHA wmoim/eccodes:x.y.z
docker image push wmoim/eccodes:x.y.z
