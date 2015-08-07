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
>昨天其实没有搞什么东西，从姐姐家看完电影回来的路上，一直在想为什么我一直做出来东西，为什么我老是做一点就放弃，做东西一难就莫名烦躁也就不去好好分析，直接就放弃了。其实细细想来可能我是怕失败吧，怕承认自己不行吧，遇到问题总是不正面面对，老是幻想走曲线救国，明明就是一种逃避啊！问题没那么难，总是有不会的，坚持下去就好，现阶段应该碰不到坚持下去也做不好的事情。等我准备好了再去做一件事情，本质上也是逃避，不敢面对失败，怕自己不行。如果一直这样不会有进步，转来转去还是远点，不改变永远都是这个样子。
<br/>
改变心态，我的目标就是利用flask做一个网站，哪怕抄也先抄一个出来，**目的是做网站，不是学习！**,**目的是做网站，不是学习！**,**目的是做网站，不是学习！**,先做成这件事情再说。











 
