 ## Lists
 
>Date: 2023-03-05  
>Category: [00ComputerScience](links/00ComputerScience.md)
>Tags: #python #programming

Lists are mutable
You can concatenate lists
You can slice lists
```python
my_list = list()
my_list.append("a")
my_list.append(1)
my_list.append([1, 2])

for i in range(len(my_list)):
	#will iterate through the whole list, i becomes equal to the current index

my_list.sort()  # sorts the list in descending orde
len(my_list)    # returns the length of the list
max(my_list)    # looks for maximum value element int the list
min(my_list)    # looks for minimum value element in the list
sum(my_list)    # summs all values in the list
my_list.split() # splist a string by a character (if provided) and returning a list
# by default split() uses space as a character
# split treats spaces as single space

```

---
- [Home](https://heartthymes.github.io)