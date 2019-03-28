#ANPSC Docker - 快速构建ANPSC容器环境

快速构建开发、测试、生产Docker + Alpine + PHP7 + Nginx + Composer + Supervisor + Crontab + Laravel 的Docker 容器应用环境


##主要特性

+ 基于[Alpine Linux](https://alpinelinux.org/) 最小化Linux环境加速构建镜像。 
+ 支持Nginx虚拟站点、SSL证书服务。配置参考Nginx中`cert`与`conf.d`目录文件。

所有的容器基于Alpine Linux,默认使用`sh` shell，进入容器时使用该命令：

```bash
$ docker exec -it container_name sh
```

## 构建镜像
    git clone https://github.com/tcyfree/anpsc.git
    docker build --no-cache -t anpsc:v1 .
    
## 启动镜像
    docker run -d -p 8096:80 --name=anpsc-v1 anpsc:v1
 
![phpinfo](https://github.com/tcyfree/anpsc/blob/master/phpinfo.png)
    
## 进入镜像容器内
    docker exec -it anpsc-v1 sh

        

## 推送镜像
    docker login # 先登录
    
    docker tag anpsc:v1 tcyfree/anpsc:v1
    
    docker push tcyfree/anpsc:v1

本镜像地址：https://hub.docker.com/r/tcyfree/apnsc

## 相关文档 ：https://segmentfault.com/a/1190000018415600
