Qt Quick模块是编写QML应用程序的标准库。Qt QML模块提供QML引擎和语言基础设施，  
Qt Quick模块提供了QML API，它提供QML类型，用于创建带有QML语言的用户界面，以及用于扩展QML的C++API。  
一个.qml文档包括两个部分，导入和使用QtQuick模块， 定义一个对象层次结构  
QML文档中的对象声明定义了在可视场景中显示的内容。Qt Quick为所有用户界面提供基本的构建块，例如用于显示图像和文本的对象，以及用于处理用户输入的对象。  
使用QML定义用户界面的最大好处之一是，它允许用户界面设计人员定义应用程序使用简单的JavaScript表达式对事件作出反应，在QML中，我们将这些事件称为信号，这些信号由信号处理程序处理。  
QML语言允许属性以多种方式相互绑定，从而支持高度动态的用户界面。  
### Component
completed()：在对象被实例化之后发出，在启动完整的QML环境之后，可以使用它来执行脚本代码，相应的处理程序是Component.onCompleted:它可以在任何对象上声明。运行onCompleted的处理程序的顺序是未定义（随机）的。
destruction()当对象开始销毁时发射Component.onDestruction:
```qml
var component = Qt.createComponent("Button.qml");
if (component.status == Component.Ready)
    component.createObject(parent, {"x": 100, "y": 100});
```
```qml
var component = Qt.createComponent("Button.qml");

var incubator = component.incubateObject(parent, { x: 10, y: 10 });
if (incubator.status != Component.Ready) {
    incubator.onStatusChanged = function(status) {
        if (status == Component.Ready) {
            print ("Object", incubator.object, "is now ready!");
        }
    }
} else {
    print ("Object", incubator.object, "is ready immediately!");
}
```
progress属性，加载组件的过程，从0.0(没有加载)到1.0(完成)。

### 信号和处理程序事件系统
应用程序和用户界面组件需要相互通信。 例如，按钮需要知道用户已经点击它。 该按钮可以改变颜色以指示其状态或执行一些逻辑。 同样，应用程序需要知道用户是否点击按钮。 应用程序可能需要将此点击事件中继到其他应用程序。

QML具有信号和处理机制，其中信号是事件，信号通过信号处理器进行响应。 当发出信号时，调用相应的信号处理程序。 在处理程序中放置诸如脚本或其他操作的逻辑允许组件响应事件。
### 信号处理程序接收信号
MouseArea中有mouse对象可以用
## Timer
### 属性
* `interval : int`  
设置计时器时间间隔，以毫秒为单位，默认时间间隔为1000毫秒
* `repeat : bool`  
设置计时器是否重复，默认值为`false`
* `running : bool`  
设置是否启动计时器，`true`为启动，`false`为停止，默认值为`false`  
对于不重复的定时器，当定时器触发后，`running`会被置为`false`
* `triggeredOnStart : bool`  
设置当计时器启动时立即触发  
如果repeat属性设置为`true`，则会在指定时间间隔再重复触发  
如果repeat属性设置为`false`，则会在指定时间间隔再触发一次（共触发两次）
### 信号
* `triggered()`  
当定时器超时时，这个信号就会发出，对应的处理程序是：`onTriggered`.  
### 方法
* `restart()` 重启计时器  
如果计时器没有运行，它将被启动，否则它将被停止，重新设置为初始状态并启动。在调用`restart()`之后，`running`属性将置为`true`
* `start()` 启动计时器  
如果计时器已经在运行，调用该方法没有任何效果。在调用`start()`之后，`running`属性将置为`true`
* `stop()` 停止计时器  
如果计时器没有运行，调用该方法没有效果。在调用`stop()`之后，运行的属性将是`false`
