## Docker
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #docker #programming  #devops

To list containers
```bash
docker ps -a
```

To ssh in to a running container:
```bash
docker attach <container>
```

To switch user:
```bash
su -l <username>
```

### Docker building an ubuntu git routing image:

1. Pull an image:
```bash
docker pull ubuntu:latest
```

---
- [Home](https://heartthymes.github.io)