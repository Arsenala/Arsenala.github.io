---
layout:     post
title:      "搭建Cloudreve网盘"
subtitle:   "Cloudreve"
date:       2018-12-27 00:00:00
author:     "xiaochao"
header-img: "img/post-bg-Cloudreve.jpg"
header-mask: 0.3
catalog:    true
tags:
    - Docker
    - Cloudreve
---

### 1、部署Docker

    curl -sSL https://get.docker.com/ | sh
    
    systemctl start docker
    
###     2、拉取镜像

    docker pull ilemonrain/cloudreve
    
###     3、配置镜像

**command**

    docker run [-d/-t] -p 80:80 -v /cloudreve:/cloudreve -e CLOUDREVE_URL="[Cloudreve URL]" --name docker-cloudreve ilemonrain/cloudreve
    
   **示例** 
   
    docker run -t -p 80:80 -v /cloudreve:/cloudreve -e CLOUDREVE_URL="http://pan.xx.com/" --name docker-cloudreve ilemonrain/cloudreve
    
**参数说明**
    
    #-d/-t：决定是以来台执行形式启动或是前台监控形式启动
    
    使用-d参数启动，镜像将不会出口任何日记到你的Console，直接以Daemon形式启动。Deamon形式启动下，可以使用docker logs docker-cloudrevecommand显现启动日记
    
    使用-t参数启动，将会直接Attach你的镜像到你的Console，这个形式启动下，你可以直观的看到镜像的启动途中，适合于初度安装镜像，以及镜像Debug安装使用。你可以使用Ctrl+C将Docker镜像转入后台执行，使用docker logs docker-cloudreve command显现启动日记
    
    #-v /cloudreve:/cloudreve：将Docker容器中的/cloudreve目录，映照到宿主机的/cloudreve目录，冒号前面的是映照路径，冒号后的为容器中路径 (激烈提议进行映照，以确保容器中数据的safe，制止在容器意外分裂时以致数据丧失)，容器中可以映照的路径：
 
    /cloudreve：Cloudreve程序目录以及DISK文件目录
 
    /var/lib/mysql：MariaDB(MySQL)数据库文件目录
 
    #-p 80:80：暴露你的Docker容器内部的80端口，到你容器表面的80端口。目前因为开拓状态缘故，不提议修正此端口
 
    #-e CLOUDREVE_URL="[Cloudreve URL]"：Cloudreve绑定的地址，此参数务必严厉填写，不可丢掉http/https前缀和煞尾的斜杠！如http://xx.com/
    
**定时任务**

    crontab -e
    
     * * * * * curl http://pan.asoasm.com/Cron

    * * * * * mysql -ucloudreve -cloudreve -cloudreve_db_1 -AB -e "truncate table campaign_log;"









