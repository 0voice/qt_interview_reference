# 158、Qt中的指针: QPointer、QScopedPointer、 QSharedPointer、QWeakPointer、std::weak_ ptr、QSharedDataPointer？

在Qt中，指针是一个很重要的概念，Qt提供了多种指针类来帮助我们管理内存和避免内存泄漏。下面是对常见的指针类进行简要介绍：


QPointer
QPointer是Qt中的智能指针，它可以自动管理指针的生命周期，并且可以检测被管理的对象是否已经被销毁。如果被管理的对象已经被销毁，QPointer会自动将指针置为nullptr。QPointer通常用于管理QWidget对象等需要在程序运行期间动态创建和销毁的对象。

QScopedPointer
QScopedPointer是Qt中的局部智能指针，它可以自动管理指针的生命周期，并且可以在指针超出作用域时自动释放指针指向的内存。QScopedPointer通常用于管理局部变量和堆内存对象等需要在作用域结束时自动释放的对象。

QSharedPointer
QSharedPointer是Qt中的共享智能指针，它可以在多个指针之间共享同一个对象，并且可以自动管理指针的生命周期。当最后一个指向对象的QSharedPointer被销毁时，QSharedPointer会自动释放对象的内存。QSharedPointer通常用于管理需要在多个地方使用同一个对象的情况。

QWeakPointer
QWeakPointer是Qt中的弱智能指针，它类似于QSharedPointer，但是不会增加对象的引用计数。QWeakPointer通常用于在多个指针之间共享同一个对象时，避免产生循环引用问题。

std::weak_ptr
std::weak_ptr是C++11标准库中的弱智能指针，它类似于QWeakPointer，但是不是Qt所提供的。std::weak_ptr可以用于在多个指针之间共享同一个对象时，避免产生循环引用问题。

QSharedDataPointer
QSharedDataPointer是Qt中的共享数据指针，它可以在多个对象之间共享同一个数据，而不需要共享整个对象。QSharedDataPointer通常用于实现copy-on-write（COW）技术，避免不必要的复制操作。
需要注意的是，不同的指针类适用于不同的场景和需求，需要根据实际情况进行选择和使用。 
