# 157、创建signal类？ QVariant 应用？

在Qt中，创建signal类可以通过继承QObject类并使用signals关键字来声明信号。一个signal类通常包含一个或多个信号，每个信号都由一个信号名称和一个信号参数列表组成，其中信号参数列表可以为空。示例代码如下：

```
class MySignalClass : public QObject
{
    Q_OBJECT
public:
    MySignalClass(QObject *parent = nullptr) : QObject(parent) {}
signals:
    void mySignal(int value);
    void anotherSignal(QString text, int count);
};
```

在上面的代码中，MySignalClass类继承自QObject类，并使用signals关键字声明了两个信号，分别是mySignal和anotherSignal，其中mySignal信号有一个int类型的参数，anotherSignal信号有一个QString类型和一个int类型的参数。 QVariant是Qt中一个用于封装任意类型数据的类，它可以用于在不同类型之间进行数据转换。可以使用QVariant::fromXXX()函数将不同类型的数据转换为QVariant类型，如QVariant::fromInt()、QVariant::fromString()等；可以使用QVariant::toXXX()函数将QVariant类型的数据转换为其他类型，如QVariant::toInt()、QVariant::toString()等。示例代码如下：

```
QVariant var = QVariant::fromInt(123); // 将int类型的数据转换为QVariant类型
int value = var.toInt(); // 将QVariant类型的数据转换为int类型
```

在上面的代码中，QVariant::fromInt()函数将int类型的数据转换为QVariant类型，QVariant::toInt()函数将QVariant类型的数据转换为int类型。需要注意的是，QVariant类型的数据转换可能会存在精度损失和类型错误等问题，需要根据实际情况进行处理。
