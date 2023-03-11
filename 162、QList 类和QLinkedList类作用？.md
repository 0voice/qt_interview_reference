# 162、QList 类/QLinkedList类作用？

在Qt中，QList类和QLinkedList类都是用来管理数据的容器类，它们的作用和区别如下：

1. QList类 QList类是一种动态数组容器，它可以存储任意类型的数据，并且支持动态增加和删除操作。QList类的内部实现是一个可变大小的数组，可以动态调整数组的大小以适应数据的存储需求。QList类通常用于存储一组数据，并且需要对数据进行动态操作，如排序、查找等。例如：

```
QList<int> list;
list.append(1);
list.append(2);
list.append(3);
int num = list.at(1); // 获取第2个元素
list.removeLast(); // 删除最后一个元素
```

2.QLinkedList类 QLinkedList类是一种双向链表容器，它可以存储任意类型的数据，并且支持动态增加和删除操作。QLinkedList类的内部实现是一个双向链表，可以动态调整链表的大小以适应数据的存储需求。QLinkedList类通常用于存储一组数据，并且需要对数据进行动态操作，如排序、查找等。例如：

```
QLinkedList<int> list;
list.append(1);
list.append(2);
list.append(3);
int num = list.at(1); // 获取第2个元素
list.removeLast(); // 删除最后一个元素
```

需要注意的是，QList类和QLinkedList类应根据实际情况进行选择和使用。如果需要对数据进行频繁的插入和删除操作，建议使用QLinkedList类；如果需要对数据进行频繁的访问和遍历操作，建议使用QList类。 
