# 95、struct和class有什么区别？

C++中，class与struct都可以定义一个类。他们有以下两点区别：

1.默认继承权限，如果不指定，来自class的继承按照private继承处理，来自struct的继承按照public继承处理；

2.成员的默认访问权限。class的成员默认是private权限，struct默认是public权限。

以上两点也是struct和class最基本的差别，也是最本质的差别；

但是在C++中，struct进行了扩展，现在它已经不仅仅是一个包含不同数据类型的数据结构了，它包括了更多的功能。

Struct能包含成员函数、有自己的构造函数、可以有析构函数、支持继承、支持多态、支持Private、Protected、Public关键字。

如果是class的父类是struct关键字描述的，那么默认访问属性是什么？

当出现这种情况时，到底默认是public继承还是private继承，取决于子类而不是基类。

class可以继承自struct修饰的类；同时，struct也可以继承自class修饰的类，继承属性如下列描述：

class A{};

class B:A{}; // private 继承

struct B:A{}; // public 继承

最后，那么到底是使用struct，还是使用class呢？

一般来说，两个关键字都是可以的，但是由于编程规范的问题，如果要定义的是一种数据结构，那么用struct，如果是一种对象的话，那么用class。
