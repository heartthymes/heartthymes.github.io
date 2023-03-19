## Regular expressions
 
>Date: 2023-03-05  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #python #programming  

- `^`              - Matches the beginning of the line
- `$`              - Matches the end of the line
- `.`              - Matches any character
- `\s`             - Matches whitespace
- `\S`             - Matches any non-whitespace character
- `*`              - Repeats a character zero or more times
- `*?`             - Repeats a character zero or more times (non-greedy)
- `+`              - Repeats a character one or more times
- `+?`             - Repeats a character one or more times (non-greedy)
- `[aeiou]`         - Matches a single character in the listed set
- `[^XYZ]`          - Matches a single character not in the listed set
- `[a-z0-9]`        - The set of characters can include a range
- `(`              - Indicates where string extraction is to start
- `)`              - Indicates where string extraction is to end



```python
import re #regular expressions lib
```

```python
for line in hand:
	# Checks if the string start with 'From:' and returning boolean
    if re.search('^From:', line): 
	    print(line)
```

```python
x = "Some random lorem ipsum string containing numbers 17 and 42"
y = re.findall('[0-9]+', x) # returns a list [17, 42]
```

Greedy matching, is matching the longest string in case of overlapping
```python
x = "From: some text AND: some other text"
y = re.findall("^F.+:", x) # y = "From: some text AND:"
```

Not-Greedy matching
```python
x = "From: some text AND: some other text"
y = re.findall("^F.+?:", x) # y = "From: some text AND:"
```

Fine tuning string extraction
```python
x = "From user.name@examplemail.com 9 Sat"
y = re.findall("^From (\S+@\S+)") # Only matches for the strings that start with From and contain email but return only email, becasue of ( )
```

---
- [Home](https://heartthymes.github.io)
