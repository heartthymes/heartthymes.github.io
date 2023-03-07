 ## Dictionaries
 
>Date: 2023-03-05  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #python #programming  

Dictionaries are key value pair collections

```python
my_dictionary = dict()            # declare dictionary
my_dictionaty['name'] = "Vasya"   # setting a value to a key
new_dictionary = { }              # declare an empty dictionary

my_dictionary.get('name', 0) + 1  # gets value by key 'name' or sets it to 0

for k, v in my_dictionary.items():             # returns a list of key value tuples from a dictionary.
#it is possible to use both variables of an item
```

Sorting
```python
# Sorting a dict by key
d = {'a':1, 'b':10, 'c':100}
sorted(d.items()) # in asc order
sorted(d.items(), reverse=True) # in desc order
```

---
- [Home](https://heartthymes.github.io)