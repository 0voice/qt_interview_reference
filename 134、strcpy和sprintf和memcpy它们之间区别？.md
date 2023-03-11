# 134、strcpy/sprintf/memcpy它们之间区别？

strcpy、sprintf和memcpy都是C语言中的字符串和内存操作函数，它们之间的主要区别如下：


strcpy用于将一个字符串复制到另一个字符串中，比如将src字符串复制到dest字符串中。函数原型为：char *strcpy(char *dest, const char *src)；

sprintf用于将格式化的数据转换成字符串并存储到另一个字符串中，比如将格式化的数字或文本保存到buf字符串中。函数原型为：int sprintf(char *buf, const char *format, ...)；

memcpy用于将一段内存的内容复制到另一个内存中，比如将src内存的内容复制到dest内存中。函数原型为：void *memcpy(void *dest, const void *src, size_t n)；
总的来说，这三个函数的作用不同，strcpy和memcpy主要用于字符串和内存的复制，而sprintf主要用于格式化数据的转换。使用时需要结合具体的需求选择合适的函数来操作。
