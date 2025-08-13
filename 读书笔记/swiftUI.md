show inspector 选项能够手动调节ui  

单击 Xcode 窗口右上角的加号按钮 （+） 打开库，然后将 各种组件拖动到代码

需了解知识点：  
map()  
MKCoordinateRegion  
image组件后面的clipshape,overlay,shawdow等等、了解是否只有在image才能用、还有没有其他的
frame  
space()  
统一掌握这些组件的名称以及代表的意义以及用法 
hashable、codable


当你将修饰符应用于像堆栈这样的布局视图时，SwiftUI 会将该修饰符应用于组中包含的所有元素。  


list  
group  
identifiable  
NavigationSplitView  
NavigationLink   
foreach  
toggle  
.animation
@observable  
@environment    
@state  
@binding  
observation


var 声明变量

let 声明常量

值永远不会隐式转换为另一种类型。如果你需要将一个值转换为不同的类型，显式创建所需类型的实例。

```
let label = "the number"
let num = 54
let labelnum = label + String(num)
```

\\()在字符串中包含值

你可以将if和let结合使用，来处理可能缺失的值。这些值用可选类型表示。一个可选值要么包含一个值，要么包含nil，表示值缺失。在值的类型后面写一个问号（?），将该值标记为可选类型。

swith x{
case y : z
default: anything
}

for in 语法 跟python 一样

..< 生成一系列索引

```
var sum = 0
for i in 0..<3:	
	sum += i
print(sum)//3
```

函数：将参数名称和类型与函数返回类型分隔开。
函数可以嵌套、可以返回另一个函数作为其值
函数可以将另一个函数作为参数之一

对象

并发

task从同步代码中调用异步函数
任务组 withTaskGroup



































