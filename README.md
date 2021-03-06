# guoyuwei1990.github.io
### 列表
- 定义列表
> alpha = ['a', 'b', 'c', 'd', 'e', 'f', 'g']
- 列表生成
```
>>> a = [i+1 for i in range(10)]
>>> a
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```
- 访问列表中的元素
```
>>> alpha[0]
'a'
>>> alpha[3]
'd'
>>> alpha[-1]
'g'
```
- 切片
```
>>> alpha[0:4]  #列表元素的下标从0开始，第一个元素的下标为0
['a', 'b', 'c', 'd'] #从下标0开始取，下标为0的元素可以取到，为4的元素取不到
>>> alpha[3:-1] #取下标3至-1的值，不包括-1
['d', 'e', 'f']
>>> alpha[3:] #如果想取到最后一个
['d', 'e', 'f', 'g']
>>> names[::2] #每两个元素取一个
['a', 'c', 'e', 'g'] 
```
- 追加
```
>>> alpha.append('3') #只能加在最后一位
>>> alpha
['a', 'b', 'c', 'd', 'e', 'f', 'g', '3']
```
- 插入
```
>>> alpha.insert(2,'3') #2为要插入的位置，'3'为插入元素的内容
>>> alpha
['a', 'b', '3', 'c', 'd', 'e', 'f', 'g', '3']
```
- 修改
```
>>> alpha[0]='555' #
>>> alpha
['555', 'b', 'c', 'd', 'e', 'f', '9', 'g']
```
- 删除
```
# del
>>> del alpha[3] #原来列表中第4个元素'd'被删除
>>> alpha
['555', 'b', 'c', 'e', 'f', '9', 'g']
# pop 顶出
>>> alpha.pop(3) #顶出下标为3的元素
'e' #会先自动返回顶出的元素
>> alpha
['555', 'b', 'c', 'f', '9', 'g']
# remove 删除指定元素
>>> alpha.remove('555')
>>> alpha
['b', 'c', 'f', '9', 'g']
```
- 复制
```
alpha_copy = alpha.copy()
```
- 扩展

```
>>> a = [1,3,5,7]
>>> alpha.extend(a) #就是合并两个列表为一个
>>> alpha
['b', 'c', 'f', '9', 'g', 1, 3, 5, 7]
```
- 反转
```
>>> alpha.reverse()
>>> alpha
[7, 5, 3, 1, 'g', '9', 'f', 'c', 'b']
```
- 统计
```
>>> alpha.count('d') #元素'd'在列表中出现的次数
0
```
- 获取下标
```
>>> alpha.index('g') #返回元素'd'的下标
4
```
### 元祖
###### 又名只读列表,用小括号表示
```
alpha = ('a', 'b', 'c'）
```
###### 只有count和index两种方法.
### 字典
###### key-value数据类型,是无序的,key必须是唯一的
###### 其表现形式(字典还可以嵌套字典，列表)
```
player = {'03':'Wade',
          '23':'James',
          '02':'Ball',
          '30':'Curry',
          '35':'Durant',
          '11':'Irving',
          '13':'George'}
```
- 增加
```
>>> player['0']='Westbrook' 
>>> player
{'0': 'Westbrook',
 '02': 'Ball',
 '03': 'Wade',
 '11': 'Irving',
 '13': 'George',
 '23': 'James',
 '30': 'Curry',
 '35': 'Durant'}
 ```
 - 修改
```
>>> player['23']='Jordan' 
>>> player
{'0': 'Westbrook',
 '02': 'Ball',
 '03': 'Wade',
 '11': 'Irving',
 '13': 'George',
 '23': 'Jordan',
 '30': 'Curry',
 '35': 'Durant'}
 ```
 - 删除
```
>>> player.pop('02') #球哥被删除
>>> player
{'0': 'Westbrook',
 '03': 'Wade',
 '11': 'Irving',
 '13': 'George',
 '23': 'Jordan',
 '30': 'Curry',
 '35': 'Durant'}
 # 也可以用del player['02'] 
 ```
- 查找
```
>>> '23' in player
True

>>> player.get('03')
'Wade'
# 同样
>>> player['03']
'Wade'
```
- 将字典里的元素转为列表
```
>>> player.items()
dict_items([('03', 'Wade'), ('23', 'Jordan'), ('30', 'Curry'), ('35', 'Durant'), ('11', 'Irving'), ('13', 'George'), ('0', 'Westbrook')])
```
- 循环
```
>>> for i in player:
       print(i, player[i])
03 Wade
23 Jordan
30 Curry
35 Durant
11 Irving
13 George
0 Westbrook

# 或者转化为列表后取值
>>> for i,j in player.items():
        print (i,j)
03 Wade
23 Jordan
30 Curry
35 Durant
11 Irving
13 George
0 Westbrook
```
- 取值
```
player.values()
```
- 取序号
```
player.keys()
```
### 集合
###### 是一个无序的，不重复的数据组合。 主要作用：去重，做关系运算。
```
>>> list_1 = set([1,2,4,5,3,4,3,6]) #创建集合
>>> list_2 = set([1,6,8,7,97,423,4,5])
>>> print(list_1)
>>> print(list_2)
{1, 2, 3, 4, 5, 6} #自动去重
{1, 97, 4, 5, 6, 7, 8, 423}
```
- 常规操作
```
#并集 |
>>> list_1.union(list_2)
{1, 2, 3, 4, 5, 6, 7, 8, 97, 423}

#交集 &
>>> list_1.intersection(list_2)
{1, 4, 5, 6}

#子集，bool型
>>> list_1.issubset(list_2)
False

#对称差集 ^ 
>>> list_1.symmetric_difference(list_2) # 返回list_1和2中无交集的元素
{2, 3, 7, 8, 97, 423}

#差集difference - ,list1里有的，list2里没有的
>>> list_1.difference(list_2)
{2, 3}

#添加一项
>>> list_1.add(1234)
>>> print(list_1)
{1, 2, 3, 4, 5, 6, 1234}

#添加多项
>>> list_1.update([123,999])
>>> print(list_1)
{1, 2, 3, 4, 5, 6, 1234}

#删除
list_1.remove(123)

#判断是否在集合里：
x in s

#判断不在集合里：
x not in s
```
### 装饰器
###### 本质：高阶函数+嵌套函数，（嵌套函数的形参为要被修饰的函数，嵌套函数的形参为将被修饰函数的形参）
###### 其作用是：在不改变原函数代码和调用方式的前提下增加新功能。
```
import  time

def timer(func):
    def deco(name,number):
        s_time = time.time()
        func(name, number)
        e_time = time.time()
        time_left = e_time - s_time
        print("time for running info is %s" % time_left)
    return deco #返回的为deco的内存地址，如果a = time(func),a()其实就是deco()

@timer # 相当于info = timer(info)，所以运行info()就相当于运行deco()
def info(name, number):
    print (name, number)

info('kobe','#8')

#返回结果为：
kobe #8
time for running info is 5.0067901611328125e-05
```
### 生成器
###### 生成器是可以迭代的，但只可以读取它一次。因为用的时候才生成。

- 创建一个generator
```
>>> (x*x for i in range(10))
<generator object <genexpr> at 0x11192ba98>
```
- 打印生成器中的元素
```javascript
>>> g = (x*x for i in range(10))
>>> next(g) #只能不断调用next(g)，直到计算到最后一个元素，提示StopIteration错误。
0
# 一般会使用for循环将其全部打印出来 
>>> for i in g:
        print(i)
1
4
9
16
25
36
49
64
81
```
- 函数生成器
```javascript
#斐波拉契数列（Fibonacci)
def fib(i):
  n,a,b=0,0,1
  while n < i: 
    a,b=b,a+b
    yield b  #print(b)改为yield b
    n=n+1
fib (12)
#返回结果
<generator object fib at 0x11193c258>
```
- 调用方式 next()
```
f = fib(12)
# 遇到yield语句返回，再次执行时从上次返回的yield语句处继续执行。
print(f.__next__())
print(f.__next__())
print("any thing")
print(f.__next__())
print(f.__next__())

1
2
any thing
3
5
```
###模块
######模块分为三种：自定义模块,内置标准模块（又称标准库）,开源模块
-time模块
```
1. time.time()# 时间戳，当前时间减去1970年1月1日，并换算为秒

2. time.localtime() #返回当地时间，stuct time格式
time.struct_time(tm_year=2018, tm_mon=3, tm_mday=21, tm_hour=18, tm_min=59, tm_sec=57, tm_wday=2, tm_yday=80, tm_isdst=0) #dst为夏令时，0为不是夏令时

3. time.timezone() #当地时间与utc标准时间的差值

4. time.sleep() #睡几秒

5. time.gmtime() #参数为秒, 时间戳转化成struct time格式 

6. time.mktime()# struct time格式转化成时间戳

7. time.shrifttime() #strftime(format[, tuple]) -> string
>>> time.strftime("%Y-%m-%d %H:%M:%S", time.localtime())  
'2018-03-21 19:21:12'#将struct time格式转化为自定义格式的字符串

8. strptime(string, format) -> struct_time  # 将字符串转化为struct time，string要和format定义的格式一一对应

9. time.asctime() # tuple -> string，默认返回当前时间'Wed Mar 21 19:29:14 2018'

10. time.ctime() # 时间戳 -> string
```
- random模块
```
1. random.random() #返回0-1的浮点数,random.uniform()可以指定区间
2. random.randint(1,3) #随机1-3整数
3. random.randrange(1,10) # 1-9整数，不包含10
4. random.choice()
5. random.sample()
6. random.shuffle() #洗牌

# 生成随机验证码
verify_code=''
for i in range(4):
    current = random.randrange(1,10)
    if i != current:
        temp = chr(random.randrange(65,90))
    else:
        temp = random.randint(0,9)

    verify_code+=str(temp)

print(verify_code)
```
- os模块
```
1. os.getcwd() #获取当前python脚本工作的目录路径
'/Users/susanguo/Documents'

2. os.chdir('/Users/susanguo') #更改当前路径致/Users/susanguo

3. os.curdir  #返回当前目录: ('.')

4. os.makedirs('dirname1/dirname2')  #生成多层递归目录

5. s.removedirs('dirname1') #若目录为空，则删除，并递归到上一级目录，若也为空，接着删除，依此类推。可以用来清理空文件夹。

6. os.mkdir('dirname') #生成单级目录

7. os.rmdir('dirname') #删除单级空目录

8. os.listdir('dirname') #列出指定目录下的所有文件和子目录，包括隐藏文件，以列表方式打印

9. os.rename("oldname","newname") #重命名文件/目录

10. os.sep  #操作系统的路径分隔符，win下为"\\",Linux下为"/"

11. os.linesep #换行分隔符

12. os.pathsep  #输出用于分割文件路径的字符串

13. os.environ #获取系统环境变量

14. os.path.abspath(path) #返回path规范化的绝对路径(从根开始，Linux中只要以“/”开头就是绝对路径)

15. os.path.split(path)  # 将path分割成目录和文件名二元组返回

16. os.path.dirname(path)  返回path的目录。其实就是os.path.split(path)的第一个元素

17 os.name  # 输出字符串指示当前使用平台,win->'nt'; Linux->'posix'

```
- 正则表达式re模块
```
re.match() #从开头搜索
re.seatch() #匹配包含
re.findall #把所有匹配到的字符放到以列表中的元素返回
re.splitall #以匹配到的字符当做列表分隔符
re.sub      #匹配字符并替换


'.'     默认匹配除\n之外的任意一个字符
'^'     匹配字符开头
'$'     匹配字符结尾
'+'     匹配前一个字符1次或多次
'?'     匹配前一个字符1次或0次
'{m}'   匹配前一个字符m次
'|'     匹配|左或|右的字符
'(...)' 分组匹配

'\A'    只从字符开头匹配，re.search("\Aabc","alexabc") 是匹配不到的
'\Z'    匹配字符结尾，同$
'\d'    匹配数字0-9
'\D'    匹配非数字
'\w'    匹配[A-Za-z0-9]
'\W'    匹配非[A-Za-z0-9]
's'     匹配空白字符、\t、\n、\r , re.search("\s+","ab\tc1\n3").group() 结果 '\t'

>>> re.search("^C.","Ch123rismas23")
'Ch'

>>> re.search("^C.+","Ch123rismas23")
'Ch123rismas23'

>>> re.search("^C+","Ch123rismas23")
'C'

>>> re.search("[0-9]{3}","Ch123rismas23")
'123'

>>> re.findall("[0-9]{2,3}","Ch123rismas23")
['123', '23']

>>> re.search("abc|ABC","ABCBabcCD")
'ABC' #返回先匹配到

>>> re.search("abc{2}","abcabccab")
'abcc' #匹配c两次

>>> re.search("(abc){2}","abcabccab")
'abcabc' #匹配abc两次

# '(?P<name>...)' 分组匹配
>>> re.search("(?P<province>[0-9]{4})(?P<city>[0-9]{2})(?P<birthday>[0-9]{4})","371481199306143242").groupdict("city")	      
{'province': '3714', 'city': '81', 'birthday': '1993'}

>>> re.split("[0-9]+","12Ch123rismas23")	      
['', 'Ch', 'rismas', '']

>>> re.sub("[0-9]+","|","12Ch123rismas23")	      
'|Ch|rismas|'
>>> re.sub("[0-9]+","|","12Ch123rismas23", count=2) #只换前两个
'|Ch|rismas23'

```
### 面向对象
###### 三大特性：封装，继承，多态。

- Encapsulation 封装
  在类中对数据的赋值、内部调用对外部用户是透明的，这使类变成了一个胶囊或容器，里面包含着类的数据和方法
```
class nba_player: #定义类
    def __init__(self,name,number): #初始化函数，初始化的一些属性就填写在这里。其中，self代表实例本身。
        self.name = name #实例变量（静态属性），作用域为实例本身。
        self.number = number

    def score(self,score_get): #类的方法（动态属性），其实就是功能
        print("%s(#%s) shoot....%spoints!!!"%(self.name,self.number,score_get))
    def assist(self):
        print("nice pass by %s"%self.name)


p1 = nba_player('Wade', 3) #调用类即实例化，实例化时python会自动把p1通过self参数传进去
p2 = nba_player('Curry',30)
print(p1)
print(p1.assist()) #等价于nba_player.assist(p1)
print(p1.score(2+1))
print(p2.assist())
print(p2.score(3))

# 当执行p1 = nba_player('Wade', 3)，即实例化时，python的解释器其实干了两件事：：
# 1. 在内存中开辟一块空间指向p1这个变量名。
# 2. 调用nba_class这个类并执行其中的__init__(…)方法, 将p1与'Wade', 3关联起来。即nba_player.____init__(p1,'Wade', 3).
#    self.name = name , self.number = number 就是要把这几个值存到p1的内存空间里。
```

- Inheritance 继承:
一个类可以派生出子类，在这个父类里定义的属性、方法自动被子类继承.广度优先继承策略。
```
class people:
    def __init__(self,name,age):
        self.name = name
        self.age = age

    def eat(self):
        print('%s is eating'%self.name)

    def sleep(self):
        print('%s is sleeping'%self.name)

    def laugh(self):
        print('%s is laughing'%self.name)



class man(people): #继承
   def __init__(self,name,age,feature):
      people.__init__(self,name,age)#沿用父类的初始化属性，也可以'super(man,self).__init__(name,age)'
      self.feature = feature #新增的属性
      print('%s has %s'%(self.name,self.feature))

   def smoke(self):
        print('%s is smoking'%self.name)

class wonmen(people):
    def shopping(self):
        print("%s is shopping"%self.name)

m1 = man('Sherlock','36','mustache')
print(m1.sleep()) #继承的父类方法
print(m1.smoke()) #子类的方法

w1 = wonmen('Kate','24')
print(w1.shopping())
```


- 类变量与实例变量
1. 类变量存在类的内存里,不实例话也可以直接调用。共同的属性
2. 实例化时，先找实例变量，没有再找类变量
- 析构函数：在实例释放或销毁执行，通常做一些收尾工作，如关闭一些数据库链接，打开的临时文件
- 私有属性与私有方法
```
class nba_player:
    def __init__(self,name,number):
        self.name = name
        self.__number = number #私有属性

    def score(self,score_get):#私有方法：def __score(self,score_get): 无法访问
        print("%s(#%s) shoot....%spoints!!!"%(self.name,self.__number,score_get))
    def assist(self):
        print("nice pass by %s"%self.name)

p3 = nba_player('Jordan',23)

#p3.number无法访问，找不到number，私有属性外面访问不了
p3.score(60) #类的里面可以访问
```
- 静态方法
##### 通过@staticmethod装饰器实现静态方法。静态方法名义上归类管理，不可以访问实例或类变的任何属性
```
class nba_player:

    def __init__(self,name):
        self.name = name

    @ staticmethod #静态方法,不可以访问实例变量或类变量的
    def score(self,score_get):
        print("%s(#%s) shoot....%spoints!!!"%(self.name,score_get))

p = nba_player('Wade')
p.score(3)
```
调用会出以下错误，当score变成静态方法后，再通过实例调用时就不会自动把实例本身当作一个参数传给self了。

```
Traceback (most recent call last):
  File "/Users/guoyuw/PycharmProjects/2018/week 6/静态方法.py", line 12, in <module>
    p.score(3)
TypeError: score() missing 1 required positional argument: 'score_get'
```
两种方法调用
1. 调用时主动传递实例本身给score方法，即p.eat(p) 
2. 在score方法中去掉self参数，但这也意味着，在score中不能通过self.调用实例中的其它变量了
```
class nba_player:

    def __init__(self,name):
        self.name = name

    @ staticmethod #静态方法,不可以访问实例变量或类变量的
    def score(score_get): # 跟类本身没有什么关系，它与类唯一的关联就是需要通过类名来调用这个方法
        print("%s shoot....%spoints!!!"%('Wade',score_get))

p = nba_player('Wade')
p.score(3)
```
- 类方法
##### 类方法通过@classmethod装饰器实现。类方法只能访问类变量，不能访问实例变量
```
class nba_player:

    def __init__(self,name):
        self.name = name

    @ classmethod
    def score(self,score_get):
        print("%s shoot....%spoints!!!"%(self.name,score_get))

p = nba_player('Wade')
p.score(3)
```
结果报错：找不到name属性
```
  File "/Users/guoyuw/PycharmProjects/2018/week 6/类方法.py", line 11, in <module>
    p.score(3)
  File "/Users/guoyuw/PycharmProjects/2018/week 6/类方法.py", line 8, in score
    print("%s shoot....%spoints!!!"%(self.name,score_get))
AttributeError: type object 'nba_player' has no attribute 'name'
```
再定义一个类变量name
```
class nba_player:
    name = 'Kobe'
    def __init__(self,name):
        self.name = name

    @ classmethod
    def score(self,score_get):
        print("%s shoot....%spoints!!!"%(self.name,score_get))

p = nba_player('Wade')
p.score(3)

#结果为
Kobe shoot....3points!!!
```
- 属性方法
##### 属性方法的作用就是通过@property把一个方法变成一个静态属性。
```
class nba_player:

    def __init__(self,name):
        self.name = name

    @ property #把一个方法变为静态属性
    def assist(self):
        print("nice pass by %s" % self.name)

p = nba_player('Wade')
p.assis()
```
返回报错:NoneType is not callable, 此时assit已经变成一个静态属性了,不再是方法，调用已经需要()，直接p.assist就可以了

```
Traceback (most recent call last):
  File "/Users/guoyuw/PycharmProjects/2018/week 6/属性方法.py", line 11, in <module>
    p.assist()
TypeError: 'NoneType' object is not callable
```
正常调用
```
p = nba_player('Wade')
p.assist

#返回结果
nice pass by Wade
```
### Numpy
- numpy创建array
```
>>> import numpy as np #导入numpy
>>> a = np.array([[1,2,3],
             [4,5,6]])
>>> print(a)
[[1 2 3]
 [4 5 6]] 
>>> a = np.ones((3,4))#生成全部为1，三行四列的矩阵
[[1. 1. 1. 1.]
 [1. 1. 1. 1.]
 [1. 1. 1. 1.]]
# 可以通过dtype定义元素类型
>>> a = np.ones((3,4),dtype=np.int64)
[[1 1 1 1]
 [1 1 1 1]
 [1 1 1 1]]
 # arange相当于python中的range
 >>> a = np.arange(2,20,2)#生成2到20之间，步长为2的数列
 [ 2  4  6  8 10 12 14 16 18]
# 通过reshape可以定义矩阵的行列数
>>> a = np.arange(12).reshape(3,4)
[[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]]
 # 生成线段 linspace
 >>> a = np.linspace(1,10,5) #从1开始到10，步长为20的线段
[ 1.    3.25  5.5   7.75 10.  ]
# 可以reshape
>>> a = np.linspace(1,10,6).reshape(2,3)
[[ 1.   2.8  4.6]
 [ 6.4  8.2 10. ]]
```
- numpy的基础运算
1. 数列的运算
```
>>> import numpy as np
>>> a = np.array([10,20,30,40]) #返回[10 20 30 40]
>>> b = np.arange(4) #返回[0 1 2 3]
>>> c = 10*np.sin(a) #调用三角函数sin
# 判断值的大小
>>> print(b<3)
[ True  True  True False]#元素里小于3返回true
```
2. 矩阵的运算
```
>>> a = np.array([[10,20],
             [30,40]])
[[10 20]
 [30 40]]
>>> b = np.arange(4).reshape(2,2)
[[0 1]
 [2 3]]
>>> c = a*b #点乘
[[  0  20]
 [ 60 120]]
# 矩阵运算 用dot
>>> c = np.dot(a,b) #也可以用a.dot(b)
[[ 40  70]
 [ 80 150]]

>>> a = np.random.random((2,4)) #生成0-1之间随机2x3的矩阵
>>> np.sum(a) #a中所有元素求和，类似还有np.min()，np.max()，np.mean()
# 通过axis=0，1来定义逐行逐列
>>> np.sum(a,axis = 1)#a中的元素逐行求和，axis = 0为逐列

>>> a = np.arange(2,14).reshape(3,4)
[[ 2  3  4  5]
 [ 6  7  8  9]
 [10 11 12 13]]
>>> np.argmin(a)#搜索最小值的索引
0
np.sort(a) #将元素按从小到大排序
a.T #a的转置
# clip功能
>>> np.clip(a,3,6) #将a中小于3的元素替换为3，大于6的元素替换为6
[[3 3 4 5]
 [6 6 6 6]
 [6 6 6 6]]
 ```
 - 索引
 ```
 >>> a = np.arange(3,15)
 [[ 3  4  5  6]
 [ 7  8  9 10]
 [11 12 13 14]]
 
 >>> print(a[2])#返回第三行
 [11 12 13 14]
>>> print(a[1][1]) #返回第二行第二列，也可以a[1,1]
8
>>> print(a[1,:]) #返回第二行所有
[ 7  8  9 10]
# 第一列所有数a[:,0]，返回[ 3  7 11]
>>> a[:,1:3]#返回第二列第三列
[[ 4  5]
 [ 8  9]
 [12 13]]

# 打印出每一行
for row in a:
    print(row)

# 打印每一列
for column in a.T:
    print(column)
# 打印每一个元素
for item in a.flat:
    print(item)
```
- 合并
```
>>> import numpy as np
    a = np.array([1,1,1])
    b = np.array([2,2,2])
    c = np.vstack((a,b)) #a,b纵向合并
[[1 1 1]
 [2 2 2]] 

>>> np.hstack((a,b)) #横向合并
[1 1 1 2 2 2]    
 
 #把横向的数列转为纵向
 c = a.reshape(a.size,1)
 
 # newaxis可以增加纬度
 a[:,np.newaxis] #纵向增加纬度
 [[1]
 [1]
 [1]]
>>> a = np.array([1,1,1])[:,np.newaxis]
    b = np.array([2,2,2])[:,np.newaxis]
    print(np.hstack((a,b)))
[[1 2]
 [1 2]
 [1 2]]

# 通常用concatenate来替代vstack和hstack，进行多项的合并
>>> c = np.concatenate((a,b,a), axis=1) #纵向合并a，b，a
[[1 2 1]
 [1 2 1]
 [1 2 1]]
```
- 分割
```
# split
import numpy as np
a = np.arange(12).reshape(3,4)
[[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]]
c = np.split(a,2,axis=1) #将c按纵向分为两块，axis = 0为横向分割
# 如果是想将4列分为三块，用np.array_split(a,3,axis=1)
```

- copy
```
import numpy as np
a = np.arange(12).reshape(3,4)
b=a.copy() #deep copy
c = a
a[0,0]=123 #改变a的第一个元素
# b中元素不变
[[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]]
# c中第一个元素随之改变
[[123   1   2   3]
 [  4   5   6   7]
 [  8   9  10  11]]
 ```
### pandas
```
import pandas as pd
import numpy as np # 一般将numpy和pandas配合使用
s = pd.Series([1,2,6,np.nan,44,1])
