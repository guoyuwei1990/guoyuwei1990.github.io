# guoyuwei1990.github.io
### 列表
- 定义列表
> alpha = ['a', 'b', 'c', 'd', 'e', 'f', 'g']
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
