
### PEP8 Styles

### Miscs
1. str, bytes, unicode
	* bytes包含8位数字
	* str包含unicode码
	* 通过utf-8 map unicode char to binary data(8-bit value)
	* encode(), decode()
	* 在python程序的消息接口处，例如前后端分界线，需要做encode, decode
	* Python代码核心应该使用str 

### Generator
1. **Conceptions**
	* list comprehension的问题在于当input很大时，它会eagerly计算所有值
	* Generator不会再运行时计算所有output,而是会提供一个iterator进行lazy calc.
	* 写法就是把list comprenshion方括号改成圆括号
2. **Miscs**
3. **Examples**
	* ```it = (len(x) for x in open('/tmp/my_file.txt')```, .....,  ```print(next(it))```
	
### Iterator & Iterable
1. 

### List Comprehensions
1. **Conceptions**
	* Python内置的用来生成**list**的表达式
	* 可以迭代list, tuple, dict, set
2. **Miscs**
	* 应用：根据已知的一个list通过各种操作创建一个新的list
	* If the expression is a tuple (e.g. the (x, y) in the previous example), it must be parenthesized.
	* 表达式如果想返回多个结果，把它变成tuple
	
3. **Examples**
	* ```[x * x for x in range(1, 11)]```
	* ```[x * x for x in range(1, 11) if x % 2 == 0]```
	* ```[m + n for m in 'ABC' for n in 'XYZ']```
	* ```d = {'x': 'A', 'y': 'B', 'z': 'C' } [k + '=' + v for k, v in d.items()]```
	* ```[(x, x**2) for x in range(6)]```
	* ```[[row[i] for row in matrix] for i in range(4)]```
	* ``` chile_ranks = {'ghost' : 1, 'habanero': 2, 'cayenne': 3}```
	  ```rank_dict = {rank: name for name, rank in chile_ranks.items()}```
	* ```chile_rank_set = {len(name) for name in rank_dict.values()}```

### Enumerate
1. **Conceptions**
	* 当需要同时知道index和值时使用
	* 生成一个生成器
2. **Examples**
	* ``` for i, flavor in enumerate(flavor_list, 1): 
		print('%d: %s' % (i, flavor))```

### Slice
1. 可切的对象
	* list -> list
	* str -> str
	* tuple -> tuple
	* bytes -> bytes
	* 实现了下列方法的类
		* __getitem__
		* __setite__
2. 左闭右开
3. 如果从0开始，忽略0, 如果slice到结束，忽略最后一个
	* a[:5] = a[0:5]
	* a[5:] = a[5:len(a)]

### OOP


### Built-in functions
* [repr](https://docs.python.org/3/library/functions.html#repr)
	* 类似java的toString()
* [enumerate](https://docs.python.org/3/library/functions.html?highlight=enumerate#enumerate)
	* 
* [zip]
	* 将两个或以上的iterators包成一个lazy generator, zip生成一个tuple包含每一个iterator的next
