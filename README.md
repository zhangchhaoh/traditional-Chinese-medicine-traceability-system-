# - 基于区块链技术的中药材溯源系统

#### 介绍
基于区块链技术的中药材溯源系统，该系统使用fabric超级账本来构建项目，使用Java sdk开发fabric,前端使用vue,后端使用springboot,系统的重要数据存储到fabric中，其他数据存储在mysql中。

#### 软件架构
软件架构说明
fabric 1.4 springboot vue
#### 介绍
一、fabric网络sdk封装
1.首先创建云服务器centos7，搭建fabric1.4。参考https://blog.csdn.net/xu710263124/article/details/116644845
2.启动网络后first-network目录下会生成crypto-config文件，将其拷贝放入云服务器的项目文件中，并且修改sdkdemo下的application.properties所有目录修改成为Linux目录。
3.添加映射关系，修改hosts文件 vim /etc/hosts， 127.0.0.1 peer0.org1.example.com peer1.org1.example.com peer0.org2.example.com peer1.org2.example.com orderer.example.com 
4.同样在本地添加映射关系修改hosts文件 0.0.0.0（服务器公网ip) peer0.org1.example.com peer1.org1.example.com peer0.org2.example.com peer1.org2.example.com orderer.example.com ，并将crypto-config文件拷贝到本地，修改sdkdemo的controller下的test的目录，并依次执行安装通道测试安装合约、实例化合约、调用合约函数、查询合约
5.在服务器上执行docker ps 查看容器中是否已经有自己编写的合约
二、nginx反向代理部署springboot及vue
1.打包herb及sdkdemo两个项目clean+package
2.修改nginx.conf文件将server_name和server的root目录修改好
3.vue npm run build 打包
4.将dist目录里的文件复制到nginx下的html自己创建文件中

