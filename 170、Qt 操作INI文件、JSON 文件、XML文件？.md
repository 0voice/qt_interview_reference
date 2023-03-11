# 170、Qt 操作INI文件、JSON 文件、XML文件？

Qt提供了三种常用的文件格式处理方式，分别是INI文件、JSON文件和XML文件。下面分别介绍如何在Qt中操作这三种文件格式。

1. 操作INI文件 INI文件是一种常用的配置文件格式，在Qt中可以通过QSettings类来读写INI文件。以下是一个例子：

```
QSettings settings("myApp.ini", QSettings::IniFormat);
// 写入配置项
settings.setValue("General/Name", "Tom");
settings.setValue("General/Age", 20);
// 读取配置项
QString name = settings.value("General/Name").toString();
int age = settings.value("General/Age").toInt();
```

2.操作JSON文件 JSON是一种轻量级的数据交换格式，在Qt中可以通过QJsonDocument类和QJsonObject类来读写JSON文件。以下是一个例子：

```
// 读取JSON文件
QFile file("data.json");
if (file.open(QIODevice::ReadOnly)) {
    QJsonParseError error;
    QJsonDocument doc = QJsonDocument::fromJson(file.readAll(), &error);
    if (error.error == QJsonParseError::NoError && doc.isObject()) {
        QJsonObject obj = doc.object();
        QString name = obj.value("name").toString();
        int age = obj.value("age").toInt();
    }
    file.close();
}
// 写入JSON文件
QJsonObject obj;
obj.insert("name", "Tom");
obj.insert("age", 20);
QJsonDocument doc(obj);
QFile file("data.json");
if (file.open(QIODevice::WriteOnly)) {
    file.write(doc.toJson());
    file.close();
}
```

3.操作XML文件 XML是一种常用的文本格式，用于表示结构化的数据，在Qt中可以通过QXmlStreamReader类和QXmlStreamWriter类来读写XML文件。以下是一个例子：

```
// 读取XML文件
QFile file("data.xml");
if (file.open(QIODevice::ReadOnly)) {
    QXmlStreamReader reader(&file);
    while (!reader.atEnd()) {
        reader.readNext();
        if (reader.isStartElement() && reader.name() == "person") {
            QString name = reader.attributes().value("name").toString();
            int age = reader.attributes().value("age").toInt();
            // 处理读取到的数据
        }
    }
    file.close();
}
// 写入XML文件
QFile file("data.xml");
if (file.open(QIODevice::WriteOnly)) {
    QXmlStreamWriter writer(&file);
    writer.setAutoFormatting(true);
    writer.writeStartDocument();
    writer.writeStartElement("persons");
    writer.writeStartElement("person");
    writer.writeAttribute("name", "Tom");
    writer.writeAttribute("age", "20");
    writer.writeEndElement();
    writer.writeEndElement();
    writer.writeEndDocument();
    file.close();
}
```

以上是Qt中操作INI文件、JSON文件和XML文件的简单示例，通过这些方法，我们可以方便地读写和处理各种数据格式的文件。 
