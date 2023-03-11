# 61、QFrame与QWidget的区别

QFrame 和 QWidget 都是 Qt 中的 GUI 组件，但是它们有一些区别：

继承关系：QFrame 继承自 QWidget，所以 QFrame 具有 QWidget 的所有功能。

功能：QFrame 提供了一个简单的框架，可以作为其他控件的容器。它还可以用来绘制简单的图形，如线条。QWidget 没有这样的功能，但是提供了基础的 GUI 组件功能，如设置尺寸和位置等。

外观：QFrame 可以有边框和背景颜色，因此外观更加丰富。QWidget 只有背景颜色，没有边框。

通常，当需要一个简单的框架时，使用 QFrame，当需要基础的 GUI 组件功能时，使用 QWidget。 
