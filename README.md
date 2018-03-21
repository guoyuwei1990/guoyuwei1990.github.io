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
