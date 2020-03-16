# Tips
- ## Access to the container with shell
```
doker exec -it <CONTAINER_NAME | CONTAINER_ID> /bin/sh
```


## Mastering Dockerfile
https://docs.docker.com/engine/reference/builder/
### FROM
Base imageをセットする

`FROM ubuntu`
### ARG
ビルド内で有効な変数

`ARG USE_GPU=1`
### RUN
コマンド実行

`RUN apt install git`
### VOLUME
指定されたディレクトリにホストのディレクトリにマウント
(マウント先は指定しないとDockerが用意したところにマウントされるらしい)
`VOLUME /myvol`

### To be continued!!
