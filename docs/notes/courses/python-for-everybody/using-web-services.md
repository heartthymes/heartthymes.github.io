## Using Web Services

>Date: 2023-03-09  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #python #programming  

XML - extendable markup language

```python
import xml.etree.ElementTree as ET

data = '''
<person>
	<name>Chuck</name>
	<phone type="intl">+1 735 303 4456</phone>
	<email hide="yes"></email>
</person>'''

tree = ET.fromstring(data)
print('Name:', tree.find('name').text)
print('Attr:', tree.find('email').get('hide'))
```

```python
import xml.etree.ElementTree as ET

input = '''
<stuff>
	<users>
		<user x="2">
			<id>001</id>
			<name>Chuck</name>
		</user>
		<user x="7">
			<id>009</id>
			<name>Brent</name>
		</user>
	</users>
</stuff>
'''

stuff = ET.fromstring(input)
lst = stuff.findall('users/user')
print('User count:', len(lst))

for item in lst:
	print('Name:', item.find('name').text)
	print('Id:', item.find('id').text)
	print('Attribute:', item.get('x'))
```

XML schema describing the interpretation of the tags
schema contains various descriptive information regarding tags in the corresponding xml file
It can contain types, min max occurrence etc.

JSON
```python
import json

data = ''' {
	"name" : "Chuck",
	"phone" : {
		"type" : "intl",
		"numer" : "+1 735 456 4578"
	},
	"email" : {
		"hide" : "yes"
	}
}'''

info = json.loads(data)
print('Name:',info["name"])
print('Hide:',info["email"]["hide"])
```

```python
import json
input = '''[
	{ 
	"id" : "001",
	"x" : "2",
	"name" : "Chuck"
	},
	{
	"id" : "009",
	"x" : "7",
	"name" : "Brent"
	}
]'''

info = json.loads(input)
print(json.dumps(info, indent=4)) # prints JSON with indent
print('User count:',len(info))
for item in info:
	print('Name:',item["name"])
	print('Id:',item["id"])
	print('Attribute:',item["x"])
```



---
- [Home](https://heartthymes.github.io)