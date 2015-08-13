# daydayup
a doc which will be recode my niubi`s life

#####7/25遇到的问题
1. CSS3部分标签已经不记得含义
2. 多处出现变量写错的低级错误


#####怎么样解决
1. 目前还未解决主要不明白的标签有
  * 浮动 absolute,relative
  * 优先级 z-index
  * 透明度 opacticy
  * 渐变属性，倒影属性
2. 通过重新写定位问题

#####总结
> 感觉这样效果不大，还是自己先写然后看视频的比较好，或则看完视频抄完一遍后自己再次手写一次


#####7/26遇到的问题
1. 因为是对照抄的所以原理不清楚导致dom结构不清楚，获取dom节点时出错调试很久
2. 调试的时候没有从客观角度出发，还是用了最麻烦最不动脑子的方法，依靠大量打印来调试

#####怎么样解决
1. 第一次实验时间比较紧只顾着出结果，没有好好消化，当然也有思维的惰性在里面，还是还能克服
2. 以后调试会从出错结果出发，逆行往上推，不偷懒尝试

#####总结
> 这一课其实重点是教一种解决问题的流程，前面部分将怎么用专业的角度去分析一个页面讲的很好，后面偏重实现前面的布局，就技术细节来说并没有讲述太多。
> 不能同以往一样只满足于实现主要功能即可，一点要做到好
> 下面的课程我要做的比教授的还要好，必须改进，这是一个好的开始

#####7/27总结
dsdsad```css
.show{#sdsdalkas
    display:show
}
.notshow{
    display:none
}
```
然后利用js获取图片所在的dom结构
```html
<div class="slide show">
    <img src="images/1.jpg"/>
</div>
```
通过添加删除属性来获得图片显示隐藏的效果，同时还将图片替换实现幻灯片效果
通过属性的切换来实现状态的改变。
关于框架部分，更牛逼搭好了结构只需要将不同的数据通过遍历代入即可


#7月30号 - CSS关于元素定位

------
一直以来都被浮动困扰不清楚其用法，今天抽时间研究了一下。其实浮动只是作为元素定位的一种方式另外还有：
> * 普通流
> * 相对定位
> * 绝对定位
> * 固定定位

要弄清楚定位就必须首先了解html元素分别行级元素与块级元素以及**包含元素**。
>行级元素不会换行都在一行内显示，而块级元素必须独占一行
```html
<div class='supermain'>
    <div class="main">
        <h2></h2>
    </div>
</div>
```
例如上面代码**main这个div为h2**的包含元素而**supermain这个div则为main的包含元素但却不是h2的包含元素，包含元素必须是相邻的包含关系**

####普通流
>普通流就是没个块级元素都一行一行显示每个项目都显示在前一个项目的下面，段落一个接一个的垂直的排列

####相对定位
>相对定位将一个元素从普通流中移动**这种移动是相对与原来在普通流中的位置移动可以上下左右的移动但是却不会影响到其它的元素**

####绝对定位
>绝对定位是将一个元素相对于它的**包含元素**移动例如h2相对于main移动,处于绝对定位的元素完全脱离了普通文档流，对其它元素的位置没有任何影响，它只相对于包含元素移动

####固定定位
>固定定位也是绝对定位的一种但是它是是元素相对于**浏览器窗口**进行移动

####浮动元素
>元素浮动可以让其脱离普通文档流，并定位到包含盒子的最左边或者右边的位置，浮动元素会成为一个周围可以浮动其它内容的块级元素，即它**影响了原来的文档流**，同时浮动也是可以对清除的，浮动元素可以选择左边的元素浮动让上面的元素不浮动


任何元素从普通文档流利脱离出来时都会产生重叠，可以用`z-index`属性控制那个元素显示在最上面一层。至于这种定位，是相对于哪个位置进行定位的包含盒子的左上角的坐标还是中心点坐标，下面继续探寻


#8月5号 Flask 概览

------
Flask是一个基于python的**MVC**web框架，帮助我们迅速搭建网站，框架的好吃是隐藏了很多的细节，我们只需要关系业务逻辑即可。我觉得主要涉及到的知识点有
> * HTTP协议 
> * 数据库相关知识
> * 模版的知识
> * 表单验证

###主要构成部分
> * 模版
> * web 表单
> * 数据库

####模版
>模版是用站位变量表示的动态变量的HTML文档，也就是我们将要展示的页面

####web表单
>表单就是HTML里面的表单,主要设计到数据的验证，安全方面的东西
```html
<form>
First name: 
<input type="text" name="firstname" />
<br />
Last name: 
<input type="text" name="lastname" />
</form>
```

###数据库
>数据库就是按照一定规则存储数据的“地方”目前数据库又分为
> * 关系型数据库SQL数据库
> * NOSQL数据库



 


#8月6号 SQL概览

------
了解了一些SQL方面的基础知识为下面的网站制作提供基础

######什么是sql
> SQL 是structured query language 的缩写结构话查询语言，我的理解就是这是一种能够组织数据并能够提供检索的语言

下面是一些基本的语法
> 搜索
```sql
/* SELECT prod_name, vend_id
FROM Products; */
SELECT prod_name
FROM Products;
```
>排序
```sql
SELECT prod_id, prod_price, prod_name
FROM Products
ORDER BY prod_price DESC, prod_name;
```
> 过滤
```sql
SELECT prod_name, prod_price
FROM Products
WHERE prod_price < 10;
```
> 通配符过滤
```sql
SELECT cust_contact
 FROM Customers
WHERE cust_contact LIKE '[^JM]%' ORDER BY cuts_contact
 ```
>汇总数据 主要有5种方式
```
AVG()    返回某列的平均值 
COUNT() 返回某列的行数 
MAX()     返回某列的最大值 
MIN()      返回某列的最小值 
 SUM()     返回某列值之和
```
>分组数据
```sql
SELECT vend_id, COUNT(*) AS num_prods
FROM Products 
GROUP BY vend_id;
```
 
#Flask

------
主要学习了flask中数据库如何配置，第一次学习的时候就躺在这里了就没有学，现在回头来看看还是存在感觉很吃力，感到吃力的原因是
> * 数据库配置比较麻烦
> * 数据库本身很多概念不清楚
> * 中间层SQLAlchemy还是很复杂
记得之前光配置数据库就搞来好几天，然后就不想弄了，后面也就放弃了，这次再试一试吧

#####配置数据库创建SQL文件
```sql
drop table if exists entries;
create table entries (
  id integer primary key autoincrement,
  title string not null,
  text string not null
);
```
>这个模式包含一个名为 entries 的表，该表中的每行都包含一个 id 、一个 title 和一个 text 。 id 是一个自增的整数，也是主键；其余的两个是字符串，且不允许为空。

#####数据库相关操作
>连接数据库
```python
def connect_db():
    """Connects to the specific database."""
    rv = sqlite3.connect(app.config['DATABASE'])
    rv.row_factory = sqlite3.Row
    return rv
```
>初始化数据库
```python
def init_db():
    with app.app_context():
        db = get_db()
        with app.open_resource('schema.sql', mode='r') as f:
            db.cursor().executescript(f.read())
        db.commit()
```

问题来了get_db()这个函数不是内置的也没有定义我怎么都初始化不成功，今天继续摸索吧，还是对数据库存在再一种恐惧感，总觉得很难

# 杂想
------
>昨天其实没有搞什么东西，从姐姐家看完电影回来的路上，一直在想为什么我一直做不出来东西，为什么我老是做一点就放弃，做东西一难就莫名烦躁也就不去好好分析，直接就放弃了。其实细细想来可能我是怕失败吧，怕承认自己不行吧，遇到问题总是不正面面对，老是幻想走曲线救国，明明就是一种逃避啊！问题没那么难，总是有不会的，坚持下去就好，现阶段应该碰不到坚持下去也做不好的事情。等我准备好了再去做一件事情，本质上也是逃避，不敢面对失败，怕自己不行。如果一直这样不会有进步，转来转去还是远点，不改变永远都是这个样子。
<br/>
改变心态，我的目标就是利用flask做一个网站，哪怕抄也先抄一个出来，**目的是做网站，不是学习！**,**目的是做网站，不是学习！**,**目的是做网站，不是学习！**,先做成这件事情再说。


#8月9日

------
#####DNS
>域名(domain name)是IP地址的代号。域名通常是由字符构成的。对于人类来说，字符构成的域名，比如www.yahoo.com，要比纯粹数字构成的IP地址(106.10.170.118)容易记忆。域名解析系统(DNS, domain name system)就负责将域名翻译为对应的IP地址。在DNS的帮助下，我们可以在浏览器的地址栏输入域名，而不是IP地址。这大大减轻了 互联网用户的记忆负担。另一方面，处于维护和运营的原因，一些网站可能会变更IP地址。这些网站可以更改DNS中的对应关系，而 保持域名不变，而IP地址更新。由于大部分用户记录的都是域名，这样就可以降低IP变更带来的影响。
DNS服务器构成一个分级(hierarchical)的树状体系。上图中，每个节点(node)为一个DNS服务器，每个节点都有自己的IP地址。树的顶端为用户电脑出口处的DNS服务器。在Linux下，可以使用cat /etc/resolv.conf，在Windows下，可以使用ipconfig /all，来查询出口DNS服务器。树的末端是真正的域名/IP对应关系记录。一次DNS查询就是从树的顶端节点出发，最终找到相应末端记录的过程。

中间节点根据域名的构成，将DNS查询引导向下一级的服务器。比如说一个域名cs.berkeley.edu，DNS解析会将域名分割为cs, berkeley, edu，然后按照相反的顺序查询(edu, berkeley, cs)。出口DNS首先根据edu，将查询指向下一层的edu节点。然后edu节点根据berkeley，将查询指向下一层的berkeley节点。这台berkeley服务器上存储有cs.berkeley.edu的IP地址。所以，中间节点不断重新定向，并将我们引导到正确的记录。
<br\>
在整个DNS查询过程中，无论是重新定向还是最终取得对应关系，都是用户计算机和DNS服务器使用DNS协议通信。用户计算机根据DNS服务器的反馈，依次与下一层的DNS服务器建立通信。用户计算机经过递归查询，最终和末端节点通信，并获得IP地址。


我之所以会挂是因为我电脑进不去apple store 所以我将DNS 改为114.114.114.114 ，因为苹果的服务器是在美国的所以这个域名能够帮助为定位到苹果的服务器的ip所在的DNS缓存服务器，而我在图书馆用i－shanghai无线是用的是中国电信的服务器。一般网络供应商（ISP）会提供动态DNS供人们使用，而我设置了静态的DNS帮助我快速定位到苹果的服务器ip，如果两者在一个域里面，我是都可以快速的访问的，但他们不在一个域，而我的DNS定向的指向了查找苹果的服务器ipDNS服务器，根本就找不到存储中国电信的服务器的ip的DNS服务器，因此解析不出来中国电信的ip，没有ip就肯定无法访问网页了。

#8月9号

------
这两天参照教程写了一个小demo发现有如下的点需要我一个一个攻破，熟悉这几个点后相信我就可以对Flask有更深入的理解了
```python
import os
import sqlite3
from flask import Flask, request, g, redirect, url_for, abort, \
    render_template, flash, session

# configuration
DATABASE = '/tmp/flasker.db'
DEBUG = True
SECRET_KEY = 'developement key'
USERNAME = 'admin'
PASSWORD = 'default'

# create our little application :)
app = Flask(__name__)
app.config.from_object(__name__)

def connect_db():
    return sqlite3.connect(app.config['DATABASE'])

# init database
from contextlib import closing

def init_db():
    with closing(connect_db()) as db:
        with app.open_resource('schema.sql', mode='r') as f:
            db.cursor().executescript(f.read())
        db.commit()


@app.before_request
def before_request():
    g.db = connect_db()


@app.teardown_request
def teardown_request(exception):
    db = getattr(g, 'db', None)
    if db is not None:
        db.close()
    g.db.close()


@app.route('/')
def show_entries():
    cur = g.db.execute('select title, text from entries order by id desc')
    entries = [dict(title=row[0], text=row[1]) for row in cur.fetchall()]
    return render_template('show_entries.html', entries=entries)


@app.route('/add', methods=['POST'])
def add_entry():
    if not session.get('logged_in'):
        abort(401)
    g.db.execute('insert into entries (title, text) values (?, ?)',
                 [request.form['title'], request.form['text']])
    g.db.commit()
    flash('New entry was successfully posted')
    return redirect(url_for('show_entries'))


@app.route('/login', methods=['GET', 'POST'])
def login():
    error = None
    print request.form
    if request.method == 'POST':
        if request.form['username'] != app.config['USERNAME']:
            error = 'Invalid username'
        elif request.form['password'] != app.config['PASSWORD']:
            error = 'Invalid password'
        else:
            session['logged_in'] = True
            flash('You were logged in')
            return redirect(url_for('show_entries'))
    return render_template('login.html', error=error)


@app.route('/logout')
def logout():
    session.pop('logged_in', None)
    flash('You were logged out')
    return redirect(url_for('show_entries'))


if __name__ == '__main__':
    app.run()
```


> * 数据库的建立，连接，取值，存储，关闭，更新
> * request 对象除了http相关信息还包含哪些信息
> * app.config配置包含哪些东西
> * jinja模版的基本用法
> * g 对象是什么东西，原理是什么，是否跟pyhton中的上下文有关系，例如with
> * session 是什么东东

下面就以这个demo为例逐一解决上述问题

######数据库相关知识
首先分别利用`init_db`和`connect_db`来初始化数据库，这里面有两个数据库文件一个`flasker.db`和`schema.sql`我不是很明白，教程上说
>关系型数据库需要一个数据库模式来定义如何储存信息，因此必须在第一次运行服务器前创建数据库模式

*这里我明天看一下Django里面是如何设置设数据库的*<br \>
demo里面用到的
>取值
```sql
select title, text from entries order by id desc
```

>插入
```sql
insert into entries (title, text) values (?, ?)',
                 [request.form['title'], request.form['text']]
```

关闭以及更新都在`init_db`这个函数里面，主要是运用了`with`语句<br \>
>	上下文管理器(context manager)是Python2.5开始支持的一种语法，用于规定某个对象的使用范围。一旦进入或者离开该使用范围，会有特殊操作被调用 (比如为对象分配或者释放内存)。它的语法形式是with...as...

当我们不需要数据库时它会自动关闭

######request对象
request对象主要是指http的请求,我以为会是一个字典，或者是一个json对象但实际上print出来却是
```python
request
<Request 'http://127.0.0.1:5000/login' [POST]>
request.form
ImmutableMultiDict([('username', u'admin'), ('password', u'default')])
type(request)
<class 'werkzeug.local.LocalProxy'>
```
原来request是一个class，好吧接下去就去研究request类，结果发现需要研究setter与getattr的用法

#8月11号

------
#####`___setter___与___getattr___`
本质上属于运算符重载，运算法重载在类方法中拦截了python原有的内置操作，重载有几个关键概念：
> * 运算符重载让类拦截常规的Python运算。
> * 类可重载所有Python表达式运算符。
> * 类也可重载打印、函数调用、属性点号运算等内置运算。
> * 重载使类实例的行为像内置类型。
> * 重载是通过提供特殊名称的类方法来实现的。



> `___getattr___` <br \> 
> 重载 点号运算     <br \> 
> 调用 x.undefine <br \> 

> `___setattr___` <br \> 
> 重载 属性赋值语句     <br \> 
> 调用 x.any = value <br \> 

```python
>>> class empty:
...     """docstring for empty"""
...     def __getattr__(self, attrname):
...             if attrname == 'age':
...                     return 40
...             else:
...                     raise AttributeError, attrname
... 
>>> X = empty()
>>> X.age
40
>>> X.name
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "<stdin>", line 7, in __getattr__
AttributeError: name
```


“在这里，empty类和其实例X本身并没有属性，所以对X.age的存取会转至__getattr__方法” <br \>



```python
>>> class accesscontrol:
...     """docstring for empty"""
...     def __setattr__(self, attr, value):
...             if attr == 'age':
...                     self.__dict__[attr] = value
...             else:
...                     raise AttributeError, attr + 'not allowed'
... 
>>> X = accesscontrol()
>>> X.age
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: accesscontrol instance has no attribute 'age'
>>> X.age = 40
>>> X.age
40
>>> X.name = 'hello'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "<stdin>", line 7, in __setattr__
AttributeError: namenot allowed
>>> 
```

“有个相关的重载方法`__setattr__`会拦截所有属性的赋值语句。如果定义了这个方法，`self.attr=value会变成self.__setattr__('attr',value)。这一点技巧性很高，因为在__setattr__中对任何self属性做赋值，都会再调用__setattr__，导致了无穷递归循环（最后就是堆栈溢出异常）。`如果想使用这个方法，要确定是通过对属性字典做索引运算来赋值任何实例属性的（下一节讨论）。也就是说，是使用`self.__dict__['name']=x，而不是self.name=x。`


###8月12日 Werkzeug WSGI

------
看完运算符重载，然后回去再看flask框架发现还是很吃力，然后百度原来flask主要是基于werkzeug封装而成的，网上回答推荐如果要了解flask框架得从三个方面
> 1. 是否对Flask的主要API都很熟悉了，是否知道一个Flask app的完整工作流程
> 2. 是否熟悉B/S这种架，是否熟悉相关网络协议（HTTP,TCP），是否清楚客户端发送请求，服务器处理响应请求的过程及其细节
> 3. 是否熟悉Python web开发的网关接口协议（WSGI）

这3点在我脑海里一点印象多没有，还是一个一个慢慢解决吧，参照<a  href='http://werkzeug-docs-cn.readthedocs.org/zh_CN/latest/tutorial.html#id1'>Werkzeug指南</a>例子写了一个demo
```python
import os
import redis
import urlparse
from werkzeug.wrappers import Request, Response
from werkzeug.routing import Map, Rule
from werkzeug.exceptions import HTTPException, NotFound
from werkzeug.wsgi import SharedDataMiddleware
from werkzeug.utils import redirect
from jinja2 import Environment, FileSystemLoader

class Shortly(object):

    def __init__(self, config):
        self.redis = redis.Redis(config['redis_host'], config['redis_port'])

    def dispatch_request(self, request):
        return Response('Hello World!')

    def wsgi_app(self, environ, start_response):
        request = Request(environ)
        response = self.dispatch_request(request)
        return response(environ, start_response)

    def __call__(self, environ, start_response):
        return self. wsgi_app(environ, start_response)


def create_app(redis_host='localhost', redis_port=6379, with_static=True):
    app = Shortly({
        'redis_host':       redis_host,
        'redis_port':       redis_port
    })
    if with_static:
        app.wsgi_app = SharedDataMiddleware(app.wsgi_app, {
            '/static':  os.path.join(os.path.dirname(__file__), 'static')
        })
    return app
    
 if __name__ == '__main__':
    from werkzeug.serving import run_simple
    app = create_app()
    run_simple('127.0.0.1', 5000, app, use_debugger=True, use_reloader=True)
```
发现理解起来很吃力，这还不算`redis`方面的，以及python的一些用法如`___call___`
教程一直在强调这是一个基于WSGI的应用，WSGI是web servers gateway interface的意思，而所有的WSGI应用都遵循一定的规则例如下面的例子
```python
from werkzeug.wrappers import Response

 def application(environ, start_response):
    response = Response('Hello World!', mimetype='text/plain')
    return response(environ, start_response)
```
但是environ， start_response 是什么我不知道，这个函数能够干什么，然后就又去看WSGI协议是个什么东东.就有去搜了一篇文章<a href='http://segmentfault.com/a/1190000003069785'>WSGI简介</a>了解到`WSGI`是一个规范定义了web服务器如何与python应用程序进行交互，文章里强调WSGI存在的意义：
> * 让web服务器知道如何调用python应用，并把客户端的请求传递过去
> * 让python应用程序知道客户端的请求是什么，以及如何把请求的结果返回给web服务器

总之就是实现了web server端与python应用之间的交流,至于上面的environ以及start_response参数文章里也给出了解释
######environ参数
>environ参数是一个Python的字典，里面存放了所有和客户端相关的信息，这样application对象就能知道客户端请求的资源是什么，请求中带了什么数据等。environ字典包含了一些CGI规范要求的数据，以及WSGI规范新增的数据，还可能包含一些操作系统的环境变量以及Web服务器相关的环境变量

######start_response参数
>start_response是一个可调用对象，接收两个必选参数和一个可选参数：
* status: 一个字符串，表示HTTP响应状态字符串
* response_headers: 一个列表，包含有如下形式的元组：(header_name, header_value)，用来表示HTTP响应的headers
* exc_info（可选）: 用于出错时，server需要返回给浏览器的信息

好了总算稍微了解了一点WSGI，今天再回过头来看werzeug吧

##<em>PS:买的<a href='http://book.douban.com/subject/6862061/'>计算机科学概论</a>应该明天到，从后天开始每天早上会花上一个小时看这本书补补基础</em>


###8月13日 不对劲啊

------
对着<a  href='http://werkzeug-docs-cn.readthedocs.org/zh_CN/latest/tutorial.html#id1'>Werkzeug指南</a>敲,敲完发现很多地方还是不理解
> 1. 如何起server
> 2. 如何传递模板
> 3. 如何解析路由
> 4. 数据库redis的相关方面
> 5. 等等
去看源码，发现连最简单的一个模块都看不懂什么意思
```python
class module(ModuleType):
    """Automatically import objects from the modules."""

    def __getattr__(self, name):
        if name in object_origins:
            module = __import__(object_origins[name], None, None, [name])
            for extra_name in all_by_module[module.__name__]:
                setattr(self, extra_name, getattr(module, extra_name))
            return getattr(module, name)
        elif name in attribute_modules:
            __import__('werkzeug.' + name)
        return ModuleType.__getattribute__(self, name)

    def __dir__(self):
        """Just show what we want to show."""
        result = list(new_module.__all__)
        result.extend(('__file__', '__path__', '__doc__', '__all__',
                       '__docformat__', '__name__', '__path__',
                       '__package__', '__version__'))
        return result
 ```
 这还只是导入模块的部分，但是我连为什么这样做不清楚，其他函数看了一下发现都是一些底层原理的实现，很多概念我都没有，这样看效果太低，挫折感太强了，我一直都是这样干的，这样肯定不会学会，我又陷入`先把所有东西都学好，再回来搞东西`这样的怪圈中了，再这样下去我估计我要看到计算是怎么一回事情了，要搞玄学了！<br\>
 
 <em>不能散开精力干这种效率很低的事情，`首要目标是先建立网站`至于底层实现，服务器原理什么的，打包机构，暂且不管以后再说<\em>
 今天会再回头看一遍我之前的flask例子，把阻止我进一步搞下去的东西再梳理一遍，以及我最终要实现什么效果再整理一下。
 
 
 
 











 
