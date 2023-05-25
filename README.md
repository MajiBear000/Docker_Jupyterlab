# Docker_Jupyterlab
Dockerfile 设置文件参考 [https://lilogs.com/archives/1567.html](https://lilogs.com/archives/1567.html), 参数参考 [this link](https://jiajially.gitbooks.io/dockerguide/content/chapter_fastlearn/dockerfile_details.html).
## Build Image
cd 到Dockerfile 的根目录. 
```
docker build -t jupyterlab .
```

## 创建container
创建container, -d后台运行, -v挂载工作路径到本地
```
docker run -p 9000:8888 -v ~/jupyter_lab:/opt/notebooks -itd --name jupyter-lab jupyterlab
```

## 进入container
-i 交互式操作, -t 终端, 使用/bin/bash 交互式 Shell
```
docker exec -it jupyter-lab /bin/bash
```

## 使用chrome不要选择记录密码！！！ 不要选择记录密码！！！不要选择记录密码！！！
容易被黑客盗取并植入挖矿病毒（不要问怎么知道的）。一般通过docker容器植入的密码只会在容器内运行，及时停止中毒容器。

使用```top```指令查看cpu占用，占用率很高并且不占内存的极为病毒程序。记录下PID，使用```ls -l /proc/PID/exe```找到病毒路径。（该路径为在容器中的路径）

进入容器，根据刚刚的路径删除所有病毒文件。
```docker exec -it YourJupyterContainer /bin/bash```

使用```ls -a```可查看隐藏文件。

## 修改jupyter notebook密码（亡羊补牢）
在容器中，执行```jupyter notebook password```修改密码。

退出并重启容器
```
exit
docker restart YourJupyterContainer
```
