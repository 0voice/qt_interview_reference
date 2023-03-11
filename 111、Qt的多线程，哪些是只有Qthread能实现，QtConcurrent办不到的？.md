# 111、Qt的多线程，哪些是只有Qthread能实现，QtConcurrent办不到的？

1、QThread可以使用信号和槽机制，而QtConcurrent不支持。
2、QThread可以设置线程优先级，而QtConcurrent不支持。
3、QThread可以实现跨平台多线程，而QtConcurrent只能在支持C++11的平台上实现。
4、QThread可以实现更复杂的多线程任务，而QtConcurrent只能实现简单的多线程任务。
