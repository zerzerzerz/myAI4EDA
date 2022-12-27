# OpenROAD安装
- [官方教程](https://openroad.readthedocs.io/en/latest/user/BuildWithDocker.html)

```bash
git clone --recursive https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts
cd OpenROAD-flow-scripts
./build_openroad.sh -t <N> # 如果编译阶段内存爆了，就减少这个N
```

```bash
docker run -it \
    -u $(id -u ${USER}):$(id -g ${USER}) \
    -v $(pwd)/flow/platforms:/OpenROAD-flow-scripts/flow/platforms:ro \
    openroad/flow-scripts
```
- `-u`指定usered和组id
- `-v`表示硬盘挂载，后面的`ro`表示read only

进入docker之后
```bash
source ./setup_env.sh
yosys -help
openroad -help
cd flow
make
exit
```

## 网络问题
- 如果因为网络问题无法正常编译，需要考虑修改下面的点
- 打开`build_openroad.sh`查看`__docker_build()`函数，这是编译的步骤，按照[1-配置Docker.md](../OpenROAD/1-配置Docker.md)配置docker build时的代理
- `tools/yosys_util/Dockerfile`这里面，安装abc的时候，可能会出现git ssl报错，再上面加一行`git config --global http.sslverify false`即可