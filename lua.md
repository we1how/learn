- 2.1 – 值与类型

Lua 是一门动态类型语言。 这意味着变量没有类型；只有值才有类型。
Lua 中有八种基本类型： nil、boolean、number、string、function、userdata、 thread 和 table。

Lua 可以调用（以及操作）用 Lua 或 C （参见 §3.4.10）编写的函数。 

userdata 类型允许将 C 中的数据保存在 Lua 变量中。 

thread 类型表示了一个独立的执行序列，被用于实现协程 

table 是一个关联数组， 也就是说，这个数组不仅仅以数字做索引，除了 nil 和 NaN 之外的所有 Lua 值 都可以做索引。
表是 Lua 中唯一的数据结构， 它可被用于表示普通数组、序列、符号表、集合、记录、图、树等等。 对于记录，Lua 使用域名作为索引。 语言提供了 a.name 这样的语法糖来替代 a["name"] 这种写法以方便记录这种结构的使用。
当一个可以完全表示为整数的浮点数做为键值时， 都会被转换为对应的整数储存。 例如，当你写 a[2.0] = true 时， 实际被插入表中的键是整数 2 。

表、函数、线程、以及完全用户数据在 Lua 中被称为 对象： 变量并不真的 持有 它们的值，而仅保存了对这些对象的 引用。

库函数 type 用于以字符串形式返回给定值的类型。


- 2.2 环境与全局环境
  
Lua 保有一个被称为 全局环境 特别环境。它被保存在 C 注册表 （参见 §4.5）的一个特别索引下。 在 Lua 中，全局变量 _G 被初始化为这个值。
此外，所有的标准库都被加载入全局环境，一些函数也针对这个环境做操作。 你可以用 load （或 loadfile）加载代码块，并赋予它们不同的环境。


- 2.3 错误处理

   Lua 代码中调用 error 函数来显式地抛出一个错误。 如果你需要在 Lua 中捕获这些错误， 可以使用 pcall 或 xpcall 在 保护模式 下调用一个函数。
   Lua 本身只会为错误生成字符串类型的错误对象， 但你的程序可以为错误生成任何类型的错误对象
   使用 xpcall 或 lua_pcall 时， 你应该提供一个 消息处理函数 用于错误抛出时调用。 该函数需接收原始的错误消息，并返回一个新的错误消息。
   它在错误发生后栈尚未展开时调用， 因此可以利用栈来收集更多的信息， 比如通过探知栈来创建一组栈回溯信息。

- 2.4 元表

Lua 中的每个值都可以有一个 元表。 这个 元表 就是一个普通的 Lua 表， 它用于定义原始值在特定操作下的行为。、

在元表中事件的键值是一个双下划线（__）加事件名的字符串； 键关联的那些值被称为 元方法。

你可以用 getmetatable 函数 来获取任何值的元表。 Lua 使用直接访问的方式从元表中查询元方法（参见rawget https://cloudwu.github.io/lua53doc/manual.html#pdf-rawget ）。 
所以，从对象 o 中获取事件 ev 的元方法等价于下面的代码：

     rawget(getmetatable(o) or {}, "__ev")
  

  .. 连接符  
  #获取变量长度

if 条件 then  else  end  
for 条件 do  end  
while 条件 do end  
repeat until 条件  

- user input
io.read()  
io.write()  

- table {}
用for循环读取下标[i]  
插入.insert()  
.remove()  
pairs 获取键值  
.contact 连接  
{ name = "",age = 12}   

- function  
  
- working with file  
io.output() 创建文件   
io.write() 写入文件    
io.close 关闭  
io.read() 读取  
file = open("", w)  file:write()  close  

 
- custom module  
```lua
custom.lua
Mod = {
    sum = function (x,y)
        return x+y
    end
 }

function Mod.sayHello(name)
  return name
end

return Mod

main.lua

local mod = require("custom")
mod.sum(10,5)
mod.say("Mike")

```

- OOP
 



--------------------------------------------------

love.load()
love.update()
love.draw() 

love.graphics() 在屏幕画东西
love.graphics.newQuad(0, 0, QUAD_WIDTH, QUAD_HEIGHT, SPRITE_WIDTH, SPRITE_HEIGHT)：在quad中做实现帧动画
sprite = love.graphics.newImage("icon/boy_run.png")：加载图片
ove.graphics.draw(boy.sprite, quads[boy.animation.frame], boy.x, boy.y, 0, -1, 1, QUAD_WIDTH, 0)：在指定位置绘制了一个水平翻转的动画帧。

love.conf 基本配置

-------------------------------
3.17

sprite sheets   
程序布局：动态生成bricks
管理状态：
levels
粒子系统
碰撞检测
持久保存数据


3.18  
## breakout0:

### 1.实现上下键发出移动的声音

```
if love.keyboard.wasPressed('up') or love.keyboard.wasPressed('down') then
        highlighted = highlighted == 1 and 2 or 1
        gSounds['paddle-hit']:play()
    end
```

```
gSounds = {
        ['paddle-hit'] = love.audio.newSource('sounds/paddle_hit.wav', 'static'),
    }
```

```
source = love.audio.newSource(filename, type)

source:play()：开始播放音频。
source:pause()：暂停音频播放。
source:stop()：停止音频播放。
source:setVolume(volume)：设置音频的音量，volume 的取值范围是 0 到 1。
source:setLooping(loop)：设置音频是否循环播放，loop 为 true 时循环播放，false 时不循环。
```











  
