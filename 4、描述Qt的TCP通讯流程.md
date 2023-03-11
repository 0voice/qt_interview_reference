# **4、描述Qt的TCP通讯流程**

服务端：（QTcpServer）

①创建QTcpServer对象

②监听list需要的参数是地址和端口号

③当有新的客户端连接成功回发送newConnect信号

④在newConnection信号槽函数中，调用nextPendingConnection函数获取新连接QTcpSocket对象

⑤连接QTcpSocket对象的readRead信号

⑥在readRead信号的槽函数使用read接收数据

⑦调用write成员函数发送数据



客户端：（QTcpSocket）

​    ①创建QTcpSocket对象

​    ②当对象与Server连接成功时会发送connected 信号

​    ③调用成员函数connectToHost连接服务器，需要的参数是地址和端口号

​    ④connected信号的槽函数开启发送数据

​    ⑤使用write发送数据，read接收数据 
