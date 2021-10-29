#### Check running docker containers

```bash
docker container ls
```

#### Check available docker images

```bash
docker image ls
```

#### Copy file from docker container to host machine

```bash
docker cp <container_id>:<src-path> <local-dest-path>
```

#### Copy file from host machine to docker container

```bash
docker cp <local-dest-path> <container_id>:<src-path>
```

