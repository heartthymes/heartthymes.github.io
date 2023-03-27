## Object-Oriented programming
 
>Date: 2023-03-27  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #python #programming  

Class, object and method call:
```python
class MyClass:
	x = 0
	z = ""
	# constructor
	def __init__ (self, z):
		self.z = z
		print('Constructed!')
		
	# self is an alias to the object 
	# which is this method called on
	def myMethod(self):
		self.x = self.x + 1
		print("x:", self.x)
		print("z:", self.z)

	#destructor
	def __del__(self):
		print('Destructed!', self.x)

mc = MyClass("Z")

mc.myMethod()

# Inheritance
class MyChildClass(MyClass):
	num = 0
	def addToNum(self):
		self.num = self.num + 1
		self.myMethod()
		print("Num:",self.num)
		print("x:",self.x)
		print("z:",self.z)

mcc = MyChildClass("Y")
mcc.addToNum()


```
Constructor is called to create an object e.g. `ob = MyClass()`
Destructor is called when the reference to the object is lost e.g. variable holding it is getting reassigned `ob = 1` or program finished it's execution

---
- [Home](https://heartthymes.github.io)
- [2023-03-27](2023-03-27.md)