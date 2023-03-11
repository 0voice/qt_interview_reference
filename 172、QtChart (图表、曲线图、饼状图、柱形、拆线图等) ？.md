# 172、QtChart (图表、曲线图、饼状图、柱形、拆线图等) ？

QtChart是Qt自带的图表库，用于绘制各种类型的图表，例如曲线图、饼状图、柱形图、折线图等。使用QtChart可以方便地将数据可视化，并支持用户交互和定制化设置。下面介绍QtChart中常用的几种图表类型及其使用方法。

1. 曲线图 曲线图用于展示一段时间内某个变量的变化趋势，例如温度、湿度、压力等。使用QtChart绘制曲线图的步骤如下：

- 创建QChart对象，并设置标题和坐标轴。
- 创建QLineSeries对象，设置曲线的名称和数据。
- 将QLineSeries对象添加到QChart对象中。
- 创建一个QChartView对象，并将QChart对象设置为其父对象。
- 将QChartView对象添加到布局中。 以下是一个简单的曲线图绘制示例：

```
QChart *chart = new QChart();
chart->setTitle("Temperature");
chart->legend()->hide();
chart->createDefaultAxes();
QLineSeries *series = new QLineSeries();
series->setName("Temperature");
series->append(0, 20);
series->append(1, 22);
series->append(2, 24);
series->append(3, 26);
chart->addSeries(series);
QChartView *chartView = new QChartView(chart);
chartView->setRenderHint(QPainter::Antialiasing);
ui->chartLayout->addWidget(chartView);
```

2.饼状图 饼状图用于展示不同数据之间的比例关系，例如不同国家的GDP占比、不同产品的销售占比等。使用QtChart绘制饼状图的步骤如下：

- 创建QChart对象，并设置标题。
- 创建QPieSeries对象，设置饼状图的名称和数据。
- 将QPieSeries对象添加到QChart对象中。
- 创建一个QChartView对象，并将QChart对象设置为其父对象。
- 将QChartView对象添加到布局中。 以下是一个简单的饼状图绘制示例：

```
QChart *chart = new QChart();
chart->setTitle("Sales");
QPieSeries *series = new QPieSeries();
series->setName("Product");
series->append("Product A", 25);
series->append("Product B", 35);
series->append("Product C", 40);
chart->addSeries(series);
chart->legend()->setAlignment(Qt::AlignRight);
QChartView *chartView = new QChartView(chart);
chartView->setRenderHint(QPainter::Antialiasing);
ui->chartLayout->addWidget(chartView);
```

3.柱形图 柱形图用于展示不同数据之间的数量关系，例如不同月份的销售额、不同省份的人口等。使用QtChart绘制柱形图的步骤如下：

- 创建QChart对象，并设置标题和坐标轴。
- 创建QBarSeries对象，设置柱形图的名称和数据。
- 将QBarSeries对象添加到QChart对象中。
- 创建一个QChartView对象，并将QChart对象设置为其父对象。
- 将QChartView对象添加到布局中。 以下是一个简单的柱形图绘制示例：

```
QChart *chart = new QChart();
chart->setTitle("Sales");
chart->setAnimationOptions(QChart::SeriesAnimations);
QBarSeries *series = new QBarSeries();
series->setName("Monthly Sales");
QBarSet *set1 = new QBarSet("January");
QBarSet *set2 = new QBarSet("February");
QBarSet *set3 = new QBarSet("March");
*set1 << 100 << 200 << 150;
*set2 << 150 << 100 << 250;
*set3 << 200 << 150 << 100;
series->append(set1);
series->append(set2);
series->append(set3);
chart->addSeries(series);
chart->createDefaultAxes();
chart->legend()->setVisible(true);
QChartView *chartView = new QChartView(chart);
chartView->setRenderHint(QPainter::Antialiasing);
ui->chartLayout->addWidget(chartView);
```

4.折线图 折线图用于展示不同数据之间的趋势变化，例如不同时间段内的股票价格、不同季度的GDP增长率等。使用QtChart绘制折线图的步骤与曲线图类似。 以上是QtChart中常用的几种图表类型的绘制示例，通过QtChart，我们可以方便地将数据可视化，让数据更加直观和易于理解。 
