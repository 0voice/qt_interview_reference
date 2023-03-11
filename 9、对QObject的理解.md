# 9、对QObject的理解

QObject 类是Qt 所有类的基类。

QObject是Qt对象模型的核心。这个模型的中心要素就是一种强大的叫做信号与槽无缝对象沟通机制。你可以用 connect() 函数来把一个信号连接到槽，也可以用disconnect() 函数来破坏这个连接。为了避免永无止境的通知循环，你可以用blockSignal() 函数来暂时阻塞信号。保护函数 connectNotify() 和 disconnectNotify() 可以用来跟踪连接。

对象树都是通过QObject 组织起来的，当以一个对象作为父类创建一个新的对象时，这个新对象会被自动加入到父类的 children() 队列中。这个父类有子类的所有权。能够在父类的析构函数中自动删除子类。可以通过findChild()和findChildren() 函数来寻找子类。

每个对象都一个对象名称objectName() ，而且它的类名也可以通过metaObject()函数。你可以通过inherits() 函数来决定一个类是否继承其他的类。当一个对象被删除时，它会发射destory() 信号，你可以抓住这个信号避免某些事情。

对象可以通过event() 函数来接收事情以及过滤来自其他对象的事件。就好比installEventFiter() 函数和eventFilter() 函数。childEvent() 函数能够重载实现子对象的事件。

QObject还提供了基本的时间支持，QTimer类 提高了更高层次的时间支持。

任何对象要实现信号与槽机制，Q_OBJECT 宏都是强制的。你也需要在源原件上运行元对象编译器。不管是否真正用到信号与槽机制，最好在所有QObject子类使用Q_OBJECT宏，以避免出现一些不必要的错误。

所有的Qt widgets 都是基础QObject。如果一个对象是widget,那么isWidgetType()函数就能判断出。 
