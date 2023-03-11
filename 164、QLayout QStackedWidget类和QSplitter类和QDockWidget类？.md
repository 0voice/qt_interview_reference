# 164、QLayout QStackedWidget类/QSplitter类/QDockWidget类？

在Qt中，QLayout类、QStackedWidget类、QSplitter类和QDockWidget类都是用于创建用户界面的类，它们的作用如下：

1. QLayout类 QLayout类是Qt中用于管理控件布局的类。它可以将控件按照一定的布局方式进行排列，如水平布局、垂直布局、网格布局等。QLayout类通常用于创建复杂的用户界面，可以有效地管理控件的位置和大小。例如：

```
QHBoxLayout *layout = new QHBoxLayout;
layout->addWidget(button1);
layout->addWidget(button2);
layout->addWidget(button3);
setLayout(layout);
```

2.QStackedWidget类 QStackedWidget类是一种堆栈容器控件，它可以将多个子控件按照堆栈的方式进行管理，只显示当前的子控件，其它子控件被隐藏。QStackedWidget类通常用于创建多页应用程序，例如多个窗口之间的切换。例如：

```
QStackedWidget *stack = new QStackedWidget;
stack->addWidget(page1);
stack->addWidget(page2);
stack->addWidget(page3);
stack->setCurrentIndex(0);
```

3.QSplitter类 QSplitter类是一种分割窗口控件，它可以将窗口分割成多个部分，每个部分可以包含一个或多个子控件。QSplitter类通常用于创建可调整大小的用户界面，可以让用户自由调整窗口的大小和位置。例如：

```
QSplitter *splitter = new QSplitter(Qt::Horizontal);
splitter->addWidget(widget1);
splitter->addWidget(widget2);
splitter->addWidget(widget3);
```

4.QDockWidget类 QDockWidget类是一种停靠窗口控件，它可以将窗口停靠在主窗口的边缘或浮动在主窗口上方。QDockWidget类通常用于创建多文档界面（MDI）应用程序，可以让用户自由调整窗口的停靠位置和大小。例如：

```
QDockWidget *dock = new QDockWidget;
dock->setWidget(widget);
dock->setWindowTitle("Dock Window");
addDockWidget(Qt::LeftDockWidgetArea, dock);
```

需要注意的是，QLayout类、QStackedWidget类、QSplitter类和QDockWidget类都是用于创建用户界面的类，需要根据实际需求进行选择和使用。 
