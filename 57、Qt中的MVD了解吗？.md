# 57、**Qt中的MVD了解吗？**

Qt的MVD包含三个部分Model（模型），View（视图），代理（Delegate）。Model否则保存数据，View负责展示数据，Delegate负责Item样式绘制或处理输入。这三部分通过信号槽来进行通信，当Model中数据发生变化时将会发送信号到View，在View中编辑数据时，Delegate负责将编辑状态发送给Model层。基类分别为QAbstractItemModel、QAbstractItemView、QAbstractItemDelegate。Qt中提供了默认实现的MVD类，如QTableWidget、QListWidget、QTreeWidget等。 
