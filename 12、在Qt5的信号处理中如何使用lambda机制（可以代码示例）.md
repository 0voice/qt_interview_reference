# 12、在Qt5的信号处理中如何使用lambda机制（可以代码示例）

信号定义了，但是不写对应槽函数，直接将函数写到槽的位置。

connect(musicPlayer,SIGNAL(positionChanged(qint64)),this,SLOT(slotReflushStartTime(qint64)));

connect(musicPlayer,SIGNAL(positionChanged(qint64)),slotReflushStartTime(qint64));

直接就是将对象都不写了，直接写个函数。 
