# 74、了解Qt的QPointer吗？

QPointer

QPointer只能用于指向QObject及派生类的对象。当一个QObject或派生类对象被删除后，QPointer能自动将其内部的指针设置为0，这样在使用QPointer之前就可以判断一下是否有效乐。

QPointer对象超出作用域时，并不会删除它指向的内存对象。 
