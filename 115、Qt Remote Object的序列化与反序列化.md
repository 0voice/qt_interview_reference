# 115、Qt Remote Object的序列化与反序列化

Qt Remote Objects是一个基于Qt的远程对象系统，它可以让你在不同的进程之间共享对象。它使用Qt的序列化技术来序列化和反序列化远程对象，以便在不同的进程之间发送和接收。

Qt的序列化技术使用QDataStream类来序列化和反序列化基本的C++数据类型，QVariant和QObject的子类。它也支持自定义类型的序列化，只要实现QDataStream的operator<<和operator>>运算符重载。

Qt Remote Objects使用QDataStream来序列化和反序列化远程对象。当客户端请求远程对象时，Qt Remote Objects将使用QDataStream将远程对象序列化，然后发送给客户端。当客户端收到序列化的远程对象时，它将使用QDataStream将远程对象反序列化，然后可以访问远程对象的属性和方法。 
