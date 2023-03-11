# 98、Qt Socket通信的过程

Qt Socket通信的过程主要分为以下几步：

1. 创建Socket：使用QTcpSocket类创建Socket，并初始化连接参数；
2. 连接服务器：使用connectToHost()函数连接服务器；
3. 发送数据：使用write()函数发送数据；
4. 接收数据：使用read()函数接收数据；
5. 断开连接：使用disconnectFromHost()函数断开连接。 
