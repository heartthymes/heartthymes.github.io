## Network Programming

>Date: 2023-03-09  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #python #programming  

```python
import socket
mysock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
mysock.connect( ('data.pr4e.org', 80) ) # TCP connection via socket
cmd = 'GET /romeo.txt HTTP/1.1\r\nHost:data.pr4e.org\r\n\r\n'.encode()
mysock.send(cmd)

while True:
	data = mysock.recv(512)
	if (len(data) < 1):
		break
	print(data.decode())
mysock.close()
```

```python
import urllib.request, urllib.parse, urllib.error

fhand = urlib.request.urlopen('http://data.pr4e.org/romeo.txt')
for line in fhand:
	print(line.decode().strip())
```



---
- [Home](https://heartthymes.github.io)