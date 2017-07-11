# gcloud-bigtable-emulator 

A docker image `FROM google/cloud-sdk:alpine` that `gcloud beta emulators bigtable start` 


## Build and run

```
docker build  -t bigtable-emulator:latest .
docker run --rm -ti bigtable-emulator:latest -p 8086:8086
```

## test with [cbt](https://cloud.google.com/bigtable/docs/go/cbt-reference) on another console

```
export BIGTABLE_EMULATOR_HOST=localhost:8086

cbt -project foo -instance bar createtable foobar
```

## Push 

```
docker build -t gcloud-bigtable-emulator:latest .
docker tag gcloud-bigtable-emulator:latest docker.io/marcelcorso/gcloud-bigtable-emulator:latest
docker push docker.io/marcelcorso/gcloud-bigtable-emulator:latest
```

