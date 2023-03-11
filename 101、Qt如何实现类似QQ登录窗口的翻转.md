# 101、Qt如何实现类似QQ登录窗口的翻转

Qt可以使用QPropertyAnimation类来实现QQ登录窗口的翻转效果。

1、首先，创建一个QPropertyAnimation对象，并设置动画的目标对象、属性和时间曲线：

QPropertyAnimation *animation = new QPropertyAnimation(this, "geometry");
animation->setDuration(500);
animation->setEasingCurve(QEasingCurve::OutExpo);

2、然后，设置动画的起始值和结束值：

//设置起始值
QRect startRect(0, 0, width(), height());
animation->setStartValue(startRect);

//设置结束值
QRect endRect(width(), 0, -width(), height());
animation->setEndValue(endRect);

3、最后，启动动画：

animation->start();
