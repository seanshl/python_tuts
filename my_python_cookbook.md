
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
		
### Functions
1. 定义函数时，需要确定函数名和参数个数；
2. 如果有必要，可以先对参数的数据类型做检查；
3. 函数体内部可以用return随时返回函数结果；
4. 函数执行完毕也没有return语句时，自动return None。
5. 函数可以同时返回多个值，但其实就是一个tuple。
1. 必须参数=位置参数
2. 必须参数 -> 默认参数
3. 当函数有多个参数时，把变化大的参数放前面，变化小的参数放后面。变化小的参数就可以作为默认参数
4. Python函数在定义的时候，默认参数L的值就被计算出来了，即[]，因为默认参数L也是一个变量，它指向对象[]，每次调用该函数，如果改变了L的内容，则下次调用时，默认参数的内容就变了，不再是函数定义时的[]了。
5. 默认参数必须指向不变对象
6. 为什么要设计str、None这样的不变对象呢？因为不变对象一旦创建，对象内部的数据就不能修改，这样就减少了由于修改数据导致的错误。此外，由于对象不变，多任务环境下同时读取对象不需要加锁，同时读一点问题都没有。我们在编写程序时，如果可以设计一个不变对象，那就尽量设计成不变对象。
7. 还可以定义可变参数。顾名思义，可变参数就是传入的参数个数是可变的，可以是1个、2个到任意个，还可以是0个
8. 定义可变参数和定义一个list或tuple参数相比，仅仅在参数前面加了一个*号。在函数内部，参数numbers接收到的是一个tuple，因此，函数代码完全不变。但是，调用该函数时，可以传入任意个参数，包括0个参数：
9. Python允许你在list或tuple前面加一个*号，把list或tuple的元素变成可变参数传进去：
10. 可变参数允许你传入0个或任意个参数，这些可变参数在函数调用时自动组装为一个tuple。而关键字参数允许你传入0个或任意个含参数名的参数，这些关键字参数在函数内部自动组装为一个dict
11. 注意kw获得的dict是extra的一份拷贝，对kw的改动不会影响到函数外的extra
12. 如果要限制关键字参数的名字，就可以用命名关键字参数，例如，只接收city和job作为关键字参数。这种方式定义的函数如下：
	* ```def person(name, age, *, city, job):```
	* 理解： '*‘ 作为可变参数分隔符, 如果函数定义中已经有了一个可变参数，后面跟着的命名关键字参数就不再需要一个特殊分隔符*了
	* ```person('Jack', 24, city='Beijing', job='Engineer')```
13. 命名关键字参数可以有缺省值，从而简化调用：
14. 在Python中定义函数，可以用必选参数、默认参数、可变参数、关键字参数和命名关键字参数，这5种参数都可以组合使用。但是请注意，参数定义的顺序必须是：必选参数、默认参数、可变参数、命名关键字参数和关键字参数。
15. 所以，对于任意函数，都可以通过类似func(*args, **kw)的形式调用它，无论它的参数是如何定义的。


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
