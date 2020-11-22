





### 第一章 Python零基础语法入门



#### 1.1 Python与PyCharm安装

[Python官网](https://www.python.org)

> python
>
> python -version

[PyCharm官网](http://www.jetbrains.com/pycharm/)

```ruby
二、Homebrew的安装

1.打开终端(terminal)
2.安装命令：
      命令1:/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"（这个命令不好使会报错，如果报错尝试使用命令2）
      命令2:/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"（这是一个脚本，同样可以安装Homebrew）
3.卸载命令：
      $ cd `brew --prefix`
      $ rm -rf Cellar
      $ brew prune
      $ rm `git ls-files`
$ rm -r Library/Homebrew Library/Aliases Library/Formula Library/Contributions
      $ rm -rf .git
      $ rm -rf ~/Library/Caches/Homebrew
```



```xml
三、Homebrew的使用

1.查看Homebrew命令：brew help
2.安装任意包：brew install <packageName>，eg：brew install node
3.卸载任意包：brew uninstall <packageName>，eg：brew uninstall git
4.查询可用包：brew search <packageName>
5.查询已安装包列表：brew list
6.查看任意包信息：brew info <packageName>
7.更新Homebrew：brew update
8.Homebrew帮助信息：brew -h
8.查看brew版本：brew -v
10.更新brew版本：brew update
11.整理重复语句：open ~/.zshrc -e、open ~/.bash_profile -e
```



#### 1.2 变量和字符串

语句不要分号结束，变量不需要提前定义

##### split ( )

通过给定的分隔符，将一个字符串分割为一个列表，如果没有分隔符，将空格作为分隔符（空格、制表、换行等）

```python
a = 'www.baiidu.com'
print ( a.split ('.') )
# result [ 'www', 'b
```



##### replace ( )

```python
a = 'There is apples'
b = a.replace('is','are')
print(b)
# reulst There are apples
```



##### strrip ( )

去除两侧（不包括内部）空格的字符创，也可以指定位置。

```python
a = ' python is cool '
print(a.strip())
# result python is cool

a = '***python*is*good****'
print(a.strip('*!'))
# result python*is*good
```



##### format ( )

字符串格式化符=选择题，**网页链接部分参数可变时使用**

```python
a = '{} is my love'.forrmat('Python')
print(a)
# result Python is my love

content = input('请输入搜索内容：')
url_path = 'https://www.pexels.com/search/{}/'.format(content)
print(url_path)
```



#### 1.3 函数与控制语句

##### 函数

**脏活累活交给函数来做**

```python
def function(a,b):
return '1/2*a*b'
```

```python
def change_number(number):
hiding_number = number.replace(number[3:7],'*'*4)
print(hiding_number)
change_number('15648929354')
result 156****99354
```



##### 条件语句

```python
def count_login():
	password=input('password:')
	if password=='12345':
		print('输入成功')
	else
		print('错误，再输入')
count_login()
```



##### 循环语句

```python
for i in range(1,11):
	print(i)
# 1~10, 11不输出的
```

```python
i=0
sum=0
while i<100:
	i=i+1
	sum=sum+i
print(sum)
# result 5050
```



#### 1.4 数据结构

##### 列表

URL和爬取的数据都是列表结构

元素是可变的（增删改-爬虫很少使用）

元素是有序的（切片索引）

```python
list=['peter','lilei','wangwu','xiaoming']
print(list[0])
print(list[2:])
# result
# peter
# ['wangwu','xiaoming']
```



可容纳所有对象

```python
list=[1,1.1,'string',print(1),True,[1,2],(1,2),{'key','value'}]
```



多重循环

```python
names=['xiaoming','wangwu','peter']
ages=[23,15,58]
for name, age in zip(names,ages):
	print(name,age)
# result
# xiaoming 23
# wanngwu 15
# peter 58
```



列表推导式

```python
urls=['http://bj.xiaozhu.com/search-duanzufang-p{}-0/'.format(number)
      for number in range(1,14)]
for url in urls:
print(url)
```



##### 字典

```python
user_info={
	'name': 'xiaoming'
	'age': '23'
	'sex': 'man'
}
```



##### 元组和集合

爬虫中很少用到

```python
tuple=(1,2,3)
# 元组类似列表，元组的元素不能修改只能查看
```

```python
list = ['xiaoming', 'zhangyun', 'xiaoming']
set = set(list)
print(set)
# result {'zhangyun', 'xiaoming'}
# 集合中元素是无序的，不可以重复
```



#### 1.5 文件操作

##### 打开文件

```python
f = open('C:/Users/Administrator/Desktop/file.txt')
# r 读模式
# w 写模式
# a 追加模式
# b 二进制模式
# + 读/写模式
```



##### 读写文件

```python
f = open('C:/Users/Admministrator/Desktop/file.txt', 'w+')
f.write('hello world')
f = open('C:/Users/Admministrator/Desktop/file.txt', 'r')
content = f.read()
print(content)
# result hello world
```



##### 关闭文件

```python
f = open('C:/Users/Admministrator/Desktop/file.txt', 'r')
content=f.read()
print(content)
f.close()
```



#### 1.6 面向对象

##### 定义类

```python
class Bike:
	compose = ['frame', 'wheel', 'pedal']

my_bike = Bike()
you_bike = Bike()
print(my_bike.compose)
print(you_bike.compose)
```



##### 实例属性

```python
class Bike:
	compose = ['frame', 'wheel', 'pedal']

my_bike = Bike()
my_bike.other = 'basket'
print(my_bike.other)
```



##### 实例方法

```python
class Bike:
	compose = ['frame', 'wheel', 'pedal']
def use(self):
	print('you are riding')

my_bike = Bike()
my_bike.use()
```

```python
class Bike:
	compose=['frame', 'wheel', 'pedal']
def use(self, time):
	print('you ride {}m'.format(time*100))

my_bike= Bike()
my_bike.use(10)
```

```python
class Bike:
	compose = ['frame', 'wheel', 'pedal']
def _init_(self):
	self.other = 'basket'
def use(self, time):
	print('you ride {}m'.format(time*100))

my_bike = Bike()
print(my_bike.other)
```



##### 类的继承

```python
class Bike:
	compose = ['frame', 'wheel', 'pedal']
def _init_(self):
	self.other = 'baseket'
def use(self,time):
	print('you ride {}m'.format(time*10))

class Share_bike(Bike):
def cost(self,hour):
	print('you spent {}'.format(hour*2))

bike = Share_bike()
print(bike.other)
bike.cost(2)
```



### 第二章 爬虫原理和网页构造

#### 2.1 爬虫原理

1、模拟计算机对服务器发起Request请求

2、接收服务器端的Response内容并解析、提取所需的信号

##### 多网页爬虫流程

1、手动翻页并观察各网页的URL构成特点，构造出所有页面的URL存入列表中

2、根据URL列表一次循环取出URL

3、定义爬虫函数

4、循环调用爬虫函数，存储数据

5、循环完毕，结束爬虫程序

##### 跨页面爬虫流程

1、定义爬虫函数爬取表页的所有专题的URL

2、将专题URL存入列表中（种子URL）

3、定义爬取详细页数据函数

4、进入专题详细页面爬取详细页数据

5、存储数据，循环完毕，结束爬虫程序

#### 2.2 网页构造

HTML：房子的框架和格局结构

CSS：房子的样式装修

JavaScript：家用电器



### 第三章 我的第一个爬虫程序

#### 3.1 爬虫三大库

##### Requests库

请求网站获取网页数据

```
sudo pip3 install beautifulsoup4
Password:
```

```sublime
"cmd": ["/usr/local/bin/python3", "-u", "$file"],
```

```python
import requests
res=requests.get('http://bj.xiaozhu.com/')
print(res)
print(res.text)
```

```python
import requests
headers={
	'User-Agent':'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.183 Safari/537.36'}
res=requests.get('http://bj.xiaozhu.com/', headers=headers)
print(res)
print(res.text)
```

Chorme, 源代码，F12，F5（刷新）



**post()方法用于提交表单来爬取需要登录才能获得数据的网站**

**异常**

* ConnectionError异常，原因为网络问题（如DNS查询失败、拒绝连接等）
* Response.raise_for_status()，HTTP请求返回了一个不成功的状态码（如网页不存在，404错误）
* Timeout异常，原因为请求超时
* TooManyRedirects异常，原因为请求超过了设定的最大重定向向次数

继承自requests.exceptions.RequestException

```python
import requests
headers={
	'User-Agent':'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.183 Safari/537.36'}
res=requests.get('http://bj.xiaozhu.com/', headers=headers)
try:
	print(res)
	print(res.text)
except ConnectionError:
	print('Refused Connecting')
```

##### BeautifulSoup库

```python
import requests
from bs4 import BeautifulSoup
headers={
	'User-Agent':'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.183 Safari/537.36'}
res=requests.get('http://bj.xiaozhu.com/', headers=headers)
soup=BeautifulSoup(res.text,'html.parser')
try:
	print(soup.prettify())
except ConnectionError:
	print('Refused Connecting')
```

**解析器**

> BeautifulSoup(markup,"html.parser")
> BeautifulSoup(markup."xlml"), 速度快，容错能力强，需要安装C语言库，官方推荐
> BeautifulSoup(markup,["lxml","xml"]), 要安装C语言库
> BeautifulSoup(markup,"xml"), 要安装C语言库
> BeautifulSoup(markup,"html5lib")



**find_all()方法**

返回的是文档中符合条件的所有tag，是一个集合

> soup.find_all('div', "item")
> 查找div标签，class=“item”

> Soup.find_all('div', class='item')
> Soup.find_all('div', attrs={"class": "item"})
> attrs参数顶一个字典参数来搜索包含特殊属性的Tag



**find()方法**

返回一个Tag



**selector()方法**

> soup.selector(div.item > a > h1)
> 中国>湖南省>长沙市

```python
##page_list > ul > li:nth-child(1) > div.result_btm_con.lodgeunitname > div:nth-child(1) > span > i

import requests
from bs4 import BeautifulSoup
headers={
	'User-Agent':'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.183 Safari/537.36'}
res=requests.get('http://bj.xiaozhu.com/', headers=headers)
soup=BeautifulSoup(res.text,'html.parser')
price=soup.select('#page_list > ul > li:nth-child(1) > div.result_btm_con.lodgeunitname > div:nth-child(1) > span > i')
try:
	print(price)
except ConnectionError:
	print('Refused Connecting')
```

（1）鼠标定位数据位置，右击，弹出快捷菜单选择“检查”

（2）在网页源代码中右击所选中的元素

（3）弹出快捷菜单选择Copy Selector

```python
##page_list > ul > li > div.result_btm_con.lodgeunitname > div > span > i

import requests
from bs4 import BeautifulSoup
headers={
	'User-Agent':'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.183 Safari/537.36'}
res=requests.get('http://bj.xiaozhu.com/', headers=headers)
soup=BeautifulSoup(res.text,'html.parser')
prices=soup.select('#page_list > ul > li > div.result_btm_con.lodgeunitname > div > span > i')
try:
	for price in prices:
		print(price)
except ConnectionError:
	print('Refused Connecting')
```

```python
##page_list > ul > li > div.result_btm_con.lodgeunitname > div > span > i

import requests
from bs4 import BeautifulSoup
headers={
	'User-Agent':'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.183 Safari/537.36'}
res=requests.get('http://bj.xiaozhu.com/', headers=headers)
soup=BeautifulSoup(res.text,'html.parser')
prices=soup.select('#page_list > ul > li > div.result_btm_con.lodgeunitname > div > span > i')
try:
	for price in prices:
		print(price.get_text())
except ConnectionError:
	print('Refused Connecting')
```



**Lxml库**









### 第四章 正则表达式



### 第五章 Lxml库与Xpath语法



### 第六章 使用API



### 第七章 数据库存储



### 第八章 多进程爬虫



### 第九章 异步加载



### 第十章 表单交互与模拟登录



### 第十一章 Selenium模拟浏览器



### 第十二章 Scrapy爬虫框架

