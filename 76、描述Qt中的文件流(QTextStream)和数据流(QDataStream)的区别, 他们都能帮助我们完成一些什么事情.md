# 76、描述Qt中的文件流(QTextStream)和数据流(QDataStream)的区别, 他们都能帮助我们完成一些什么事情

- QTextStream – 文本流, 操作轻量级数据(int, double, QString), 数据写入文件中之后以文本的方式呈现。
- QDataStream – 数据流, 通过数据流可以操作各种数据类型, 包括类对象, 存储到文件中数据可以还原到内存。
- QTextStream, QDataStream可以操作磁盘文件, 也可以操作内存数据, 通过流对象可以将数据打包到内存, 进行数据的传输。
