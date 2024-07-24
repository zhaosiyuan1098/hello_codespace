# hello_codespace

## 构建docker环境 

1. 构建：
`cd ./docker && docker build -t siyuan .`
2. 执行：
`docker run -v ./:/workspace/ -it siyuan`
3. 进入：
    * 首先使用 `docker container ls -a`查看运行docker container，假设id为 abcd
    * `docker exec -it abcd sh`

## 换源

`bash <(curl -sSL https://linuxmirrors.cn/main.sh)`

## 跳转项

1. [docker教程](https://yeasy.gitbook.io/docker_practice)
2. [gdb](https://github.com/zhaosiyuan1098/learn-gdb-by-example-for-c)
3. [xmake](https://xmake.io/#/zh-cn/)