# 75、了解Qt的QSharedPointer吗？

### QSharedPointer

用于实现数据的隐式共享。Qt中大量使用了隐式共享与写时拷贝技术，例如：

```cpp
QString str1 = "abc";
QString str2 = str1;
str2[2] = "X"; 
```

第二行执行完后，str2和str1指向同一片内存数据。第三句执行时，Qt会为str2的内部数据重新分配内存。这样做的好处是可以有效地减少大片数据拷贝的次数，提高程序的运行效率。

Qt中隐式共享和写时拷贝就是利用QSharedDataPointer和QSharedData这两个类实现的。 
