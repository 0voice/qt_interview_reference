# 155、Qt 网络通信中，TCP./UDP 整体流程(服务器，客户端) ？

在Qt中，TCP/UDP网络通信的整体流程主要包括以下步骤：

服务器端的创建和监听

服务器端首先需要创建一个QTcpServer或QUdpSocket对象，用于监听客户端的连接或接收数据。创建时需要指定端口号和IP地址（如果有多个网卡，则需要指定监听的网卡地址）。然后调用listen()函数开始监听客户端的连接或数据包的到来。

客户端的连接或数据发送

客户端需要创建一个QTcpSocket或QUdpSocket对象，用于连接服务器或发送数据包。对于TCP通信，客户端需要调用connectToHost()函数连接服务器；对于UDP通信，客户端可以直接使用writeDatagram()函数发送数据包。

服务器端的响应和数据处理

当客户端连接到服务器或发送数据包时，服务器端会触发相应的信号（如newConnection()、readyRead()等），在相应的槽函数中进行响应和数据处理。对于TCP通信，服务器端需要在newConnection()槽函数中调用nextPendingConnection()函数获取客户端的QTcpSocket对象，然后在客户端的QTcpSocket对象上调用read()函数读取数据；对于UDP通信，服务器端可以直接在readyRead()槽函数中调用readDatagram()函数读取数据包。

客户端的数据接收和响应

当客户端连接到服务器或发送数据包时，客户端会触发相应的信号（如connected()、readyRead()等），在相应的槽函数中进行数据接收和响应。对于TCP通信，客户端需要在connected()槽函数中调用write()函数发送数据，然后在readyRead()槽函数中调用read()函数读取服务器端的响应数据；对于UDP通信，客户端可以直接在readyRead()槽函数中调用readDatagram()函数读取服务器端的响应数据包。

断开连接和清理资源

当通信完成或出现错误时，需要断开连接并清理资源。对于TCP通信，可以在客户端或服务器端的QTcpSocket对象上调用disconnectFromHost()函数或close()函数断开连接，并在socketDisconnected()槽函数中清理资源；对于UDP通信，不需要显式地断开连接，系统会自动管理资源。

综上所述，TCP/UDP网络通信的整体流程包括服务器端的创建和监听、客户端的连接或数据发送、服务器端的响应和数据处理、客户端的数据接收和响应，以及断开连接和清理资源。根据具体的需求，可以选择使用QTcpServer、QTcpSocket、QUdpSocket等类进行开发。
