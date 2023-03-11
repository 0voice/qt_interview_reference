# 154、Qt当中的数据流(QDataStream) 和文件流(QTextStream) 有何区别？

Qt中的数据流(QDataStream)和文件流(QTextStream)都是用于读写数据的流类，但它们有以下区别：


数据类型：数据流(QDataStream)支持Qt中的所有基本数据类型和自定义类型，如QString、QByteArray等，而文件流(QTextStream)只能读写文本数据，不支持二进制数据。

数据格式：数据流(QDataStream)是二进制格式，可以直接读写二进制数据，而文件流(QTextStream)是文本格式，只能读写文本数据，对于二进制数据需要进行编码和解码。

数据编码：文件流(QTextStream)默认使用Unicode编码，可以通过设置不同的编码格式来读写不同的文本数据，而数据流(QDataStream)不需要进行编码，它直接以二进制形式读写数据。

应用场景：数据流(QDataStream)适用于读写二进制数据，例如读写文件、网络传输等场景，而文件流(QTextStream)适用于读写文本数据，例如读写配置文件、日志文件等场景。

综上所述，数据流(QDataStream)和文件流(QTextStream)虽然都是Qt中的流类，但它们的数据类型、格式、编码和应用场景等方面有所不同，需要根据具体的需求选择合适的流类进行读写操作。 
