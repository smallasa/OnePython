## Python简介
### 1.简要
Python语言是由荷兰程序员Guido van Rossum，江湖人称“龟叔”，独立开发完成初版的。
Python 源代码遵循 GPL(GNU General Public License)协议，这是一个开源的协议，也就是说你可以免费使用和传播它，而不用担心版权的问题。


### 2.Python语言的特点
* 简单易学、明确优雅、开发速度快
* 跨平台、可移植、可扩展、交互式、解释型、面向对象的动态语言
* 大量的标准库和第三方库
* 社区活跃，贡献者多，互帮互助
* 开源语言，发展动力巨大


### 3.Python的应用方向
* 常规软件开发  
  Python支持函数式编程和OOP面向对象编程，能够承担任何种类软件的开发工作，因此常规的软件开发、脚本编写、网络编程等都属于标配能力。
* 科学计算  
  随着NumPy, SciPy, Matplotlib, Enthought librarys等众多程序库的开发，Python越来越适合于做科学计算、绘制高质量的2D和3D图像。
* 自动化运维  
  作为运维工程师首选的编程语言，Python在自动化运维方面已经深入人心，比如Saltstack和Ansible都是大名鼎鼎的自动化平台。
* 云计算  
  开源云计算解决方案OpenStack就是基于Python开发的。
* WEB开发  
  基于Python的Web开发框架，比如Django，Tornado，Flask。其中的Python+Django架构，应用范围广，开发速度快，学习门槛低。
* 网络爬虫  
  网络爬虫是大数据行业获取数据的核心工具。其中Scripy爬虫框架应用非常广泛。
* 数据分析  
  在大量数据的基础上，结合科学计算、机器学习等技术，对数据进行清洗、去重、规格化和针对性的分析是大数据行业的基石。Python是数据分析的主流语言之一。
* 人工智能  
  Python在人工智能大范畴领域内的机器学习、神经网络、深度学习等方面都是主流的编程语言，得到广泛的支持和应用。

### 4.Python的缺点
* 第一个缺点就是运行速度相对慢点，和C程序相比慢不少，这是解释型语言的通病，你的Python代码在执行时会一行一行地翻译成CPU能理解的机器码，这个翻译过程非常耗时，所以会变慢。
* 第二个问题就是GIL（Global Interpreter Lock）全局解释器锁，这是一种防止多线程并发执行机器码的互斥锁，功能和性能之间权衡后的产物。可以使用非官方的PyPy解释器或者协程机制。
* 第三个不是缺点的问题是Python2和Python3的不兼容性。


### 5.Python之禅
```bash
>>> import this
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
```
```text
优美胜于丑陋（Python 以编写优美的代码为目标）
明了胜于晦涩（优美的代码应当是明了的，命名规范，风格相似）
简洁胜于复杂（优美的代码应当是简洁的，不要有复杂的内部实现）
复杂胜于凌乱（如果复杂不可避免，那代码间也不能有难懂的关系，要保持接口简洁）
扁平胜于嵌套（优美的代码应当是扁平的，不能有太多的嵌套）
间隔胜于紧凑（优美的代码有适当的间隔，不要奢望一行代码解决问题）
可读性很重要（优美的代码是可读的）
即便假借特例的实用性之名，也不可违背这些规则（这些规则至高无上）
不要包容所有错误，除非你确定需要这样做（精准地捕获异常，不写 except:pass 风格的代码）
当存在多种可能，不要尝试去猜测而是尽量找一种，最好是唯一一种明显的解决方案（如果不确定，就用穷举法）
虽然这并不容易，因为你不是 Python 之父（这里的 Dutch 是指 Guido ）
做也许好过不做，但不假思索就动手还不如不做（动手之前要细思量）
如果你无法向人描述你的方案，那肯定不是一个好方案；反之亦然（方案测评标准）
命名空间是一种绝妙的理念，我们应当多加利用（倡导与号召）
```