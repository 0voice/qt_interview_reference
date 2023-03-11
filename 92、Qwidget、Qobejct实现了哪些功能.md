# 92、**Qwidget、Qobejct实现了哪些功能**

**QObject**

1、信号和槽的非常强大的机制,使用connect()把信号和槽连接起来并且可以用disconnect()来破坏这种连接。为了避免从不结束的通知循环，你可以调用blockSignals()临时地阻塞信号。保护函数connectNotify()和disconnectNotify()使跟踪连接成为可能。

2、QObject可以通过event()接收事件并且过滤其它对象的事件。详细情况请参考installEventFilter()和eventFilter()。一个方便的处理者，childEvent()，能够被重新实现来捕获子对象事件。

3、最后但不是最不重要的一点，QObject提供了Qt中最基本的定时器，关于定时器的高级支持请参考QTimer。

4、注意Q_OBJECT宏对于任何实现信号、槽和属性的对象都是强制的。

5、所有的Qt窗口部件继承了QObject。方便的函数isWidgetType()返回这个对象实际上是不是一个窗口部件。它比inherits(“QWidget” )快得多。

**QWidget**

1、QWidget类是所有用户界面对象的基类。
2、Widget是用户界面的基本单元：它从窗口系统接收鼠标，键盘和其他事件，并在屏幕上绘制自己。每个Widget都是矩形的，它们按照Z-order进行排序。
