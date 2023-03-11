# 103、Qt的智能指针，QSharePoint和shared_ptr有什么区别，weak_ptr呢？

Qt智能指针是一种特殊的指针，它可以指向另一个指针。它可以用来创建复杂的数据结构，如链表或树结构。

QSharePoint是一种智能指针，它可以自动管理指向的对象的内存分配和释放，从而实现自动内存管理。

shared_ptr也是一种智能指针，它可以跟踪指向的对象的引用计数，从而保证在没有任何引用的情况下，可以自动释放指向的对象。

weak_ptr是一种特殊的shared_ptr，它可以指向shared_ptr指向的对象，但不会增加指向对象的引用计数。它可以用来避免循环引用导致的内存泄漏问题。

在Qt中，指针指针（Pointer to Pointer）是一种指向指针的指针，通常用于动态分配内存或者多级指针操作。而QSharedPointer和std::shared_ptr都是C++11中的智能指针，用于管理动态内存，可以避免内存泄漏和空悬指针等问题。它们的主要区别如下：

1. QSharedPointer是Qt框架提供的智能指针，而std::shared_ptr是C++11标准库提供的智能指针。

2. QSharedPointer可以与QObject一起使用，可以自动处理QObject的引用计数，当QObject被删除时，QSharedPointer会自动释放对它的引用。而std::shared_ptr无法处理QObject的引用计数，需要手动管理。

3. QSharedPointer可以使用qSharedPointerCast进行类型转换，可以方便地将一个QSharedPointer转换为另一个QSharedPointer。而std::shared_ptr只能使用std::dynamic_pointer_cast进行类型转换。

4. QSharedPointer的默认删除器是delete，而std::shared_ptr的默认删除器是std::default_delete。

相比之下，weak_ptr则是用来解决shared_ptr循环引用问题的。当两个或多个shared_ptr相互引用时，会形成循环引用，导致内存泄漏。此时，可以使用weak_ptr来打破其中一个shared_ptr的引用，避免循环引用。weak_ptr是一种弱引用，它不会增加内存对象的引用计数，只是用来观察对象是否已经被释放，可以通过lock方法获取其对应的shared_ptr。
