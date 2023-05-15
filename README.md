# Docker_Jupyterlab
## cd 到Dockerfile 的根目录. build 镜像
```
docker build -t jupyterlab .
```

## 创建container， -d后台运行，-v挂载工作路径到本地
```
docker run -p 9000:8888 -v ~/jupyter_lab:/opt/notebooks -itd --name jupyter-lab jupyterlab
```
