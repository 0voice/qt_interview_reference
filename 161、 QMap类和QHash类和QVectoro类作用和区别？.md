# 161、 QMap类/QHash类/QVectoro类作用和区别？

在Qt中，QMap类、QHash类和QVector类都是用来管理数据的容器类，它们的作用和区别如下：

1. QMap类 QMap类是一种有序的映射容器，它可以将一个键值对映射到另一个键值对，且键值对是按照键的顺序进行排序的。QMap类通常用于对一组数据进行映射操作，常见的操作包括查找、插入、删除等。例如：

```
QMap<QString, int> map;
map.insert("Tom", 18);
map.insert("Jack", 20);
map.insert("Lucy", 17);
int age = map.value("Tom"); // 获取键为"Tom"的值
map.remove("Lucy"); // 删除键为"Lucy"的键值对
```

2.QHash类 QHash类是一种无序的哈希容器，它可以将一个键值对映射到另一个键值对，且键值对是按照哈希值进行存储的。QHash类通常用于对一组数据进行哈希操作，常见的操作包括查找、插入、删除等。例如：

```
QHash<QString, int> hash;
hash.insert("Tom", 18);
hash.insert("Jack", 20);
hash.insert("Lucy", 17);
int age = hash.value("Tom"); // 获取键为"Tom"的值
hash.remove("Lucy"); // 删除键为"Lucy"的键值对
```

3.QVector类 QVector类是一种动态数组容器，它可以存储任意类型的数据，并且支持动态增加和删除操作。QVector类通常用于存储一组数据，并且需要对数据进行动态操作，如排序、查找等。例如：

```
QVector<int> vec;
vec.append(1);
vec.append(2);
vec.append(3);
int num = vec.at(1); // 获取第2个元素
vec.removeLast(); // 删除最后一个元素
```

需要注意的是，QMap类、QHash类和QVector类应根据实际情况进行选择和使用。如果需要对数据进行排序和查找操作，建议使用QMap类；如果需要对数据进行哈希操作，建议使用QHash类；如果需要对数据进行动态操作，建议使用QVector类。 
