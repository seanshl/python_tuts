
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
	* 

### Slice

### OOP
