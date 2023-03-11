# 5、 描述UDP 之 UdpSocket通讯

UDP（User Datagram Protocol即用户数据报协议）是一个轻量级的，不可靠的，面向数据报的无连接协议。在网络质量令人十分不满意的环境下，UDP协议数据包丢失严重。由于UDP的特性：它不属于连接型协议，因而具有资源消耗小，处理速度快的优点，所以通常音频、视频和普通数据在传送时使用UDP较多，因为它们即使偶尔丢失一两个数据包，也不会对接收结果产生太大影响。所以QQ这种对保密要求并不太高的聊天程序就是使用的UDP协议。

在Qt中提供了QUdpSocket 类来进行UDP数据报（datagrams）的发送和接收。Socket简单地说，就是一个IP地址加一个port端口 。

流程：①创建QUdpSocket套接字对象 ②如果需要接收数据，必须绑定端口 ③发送数据用writeDatagram，接收数据用 readDatagram 。 
