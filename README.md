# game(逻辑)
## 设计理念
游戏服务器对外只提供一个接口， 即:

> rpc Stream(stream Game.Frame) returns (stream Game.Frame);

Frame的双向流

来自设备的数据包，通过agent后直接透传到game server, Frame大体分为两类：        
1. 链路控制（register, kick)     
2. 来自设备的透传数据包 (message)       

透传数据包格式为:      
> 协议号＋数据

在client_handler目录中对应函数进行处理，协议生成和绑定通过tools目录中的脚本进行。

## 使用
参考测试用例以及game.proto文件

## 安装
参考Dockerfile

# 环境变量
> NSQD_HOST: eg : http://172.17.42.1:4151
