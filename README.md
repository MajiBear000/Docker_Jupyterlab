# Docker_Jupyterlab
Dockerfile 设置文件参考 [https://lilogs.com/archives/1567.html](https://lilogs.com/archives/1567.html), 参数参考 [this link](https://jiajially.gitbooks.io/dockerguide/content/chapter_fastlearn/dockerfile_details.html).
## cd 到Dockerfile 的根目录. build image
```
docker build -t jupyterlab .
```

## 创建container, -d后台运行, -v挂载工作路径到本地
```
docker run -p 9000:8888 -v ~/jupyter_lab:/opt/notebooks -itd --name jupyter-lab jupyterlab
```

## 进入container, -i 交互式操作, -t 终端, 使用/bin/bash 交互式 Shell
```
docker exec -it jupyter-lab /bin/bash
```
