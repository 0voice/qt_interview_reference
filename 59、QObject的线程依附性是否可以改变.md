# 59、QObject的线程依附性是否可以改变

调用QObject::moveToThread()函数。该函数会改变一个对象及其所有子对象的线程依附性。

- 由于QObject本身是线程不安全的，因此moveToThread接口的调用必须在QObject对象所在的线程内调用。 
