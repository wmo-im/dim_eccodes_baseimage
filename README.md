# dim_eccodes_baseimage
for builder the eccodes docker base image used in various wmo software projects

### build new release
docker build -t dim_eccodes_baseimage:x.y.z . # note sha

### push image in GHCR
docker tag $SHA ghcr.io/wmo-im/dim_eccodes_baseimage:x.y.z
docker image push ghcr.io/wmo-im/dim_eccodes_baseimage:x.y.z

### push image wmoim docker-hub
docker tag $SHA wmoim/dim_eccodes_baseimages:x.y.z
docker image push wmoim/dim_eccodes_baseimage:x.y.z
