# 160、 QString与基本数据类型如何转换？

在Qt中，QString与基本数据类型之间可以进行方便的相互转换。下面是常见的转换方法：

1. 将QString转换为基本数据类型 通过QString的各种转换函数，可以将QString转换为int、float、double等基本数据类型。例如：

   ```
   QString str = "123";
   int num = str.toInt(); // 将QString转换为int类型
   float f = str.toFloat(); // 将QString转换为float类型
   double d = str.toDouble(); // 将QString转换为double类型
   ```

   2.将基本数据类型转换为QString 通过QString的静态函数，可以将int、float、double等基本数据类型转换为QString。例如：

   ```
   1. int num = 123;
      QString str = QString::number(num); // 将int类型转换为QString
      float f = 3.14;
      QString str2 = QString::number(f); // 将float类型转换为QString
   ```

   需要注意的是，QString和基本数据类型之间的转换可能会存在精度和数据溢出等问题，需要根据实际情况进行选择和处理。

  
