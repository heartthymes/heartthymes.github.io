## Installing and launching
 
>Date: 2023-03-19  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #typescript #programming 

### Installing

To install typescript fist you gonna need [Node.js](https://nodejs.org/en)

Having node installed run this command:
```bash
sudo npm install -g typescript
```
To install additional helping utilities:
```bash
sudo npm install -g ts-node
```

### Launching

Create a file with `.ts` extension. Write TS or JS in it.

First we need to compile TS in to JS:
```bash
tsc myfile.ts
```
JS file is the one that is readable by browsers, node environment, etc.
For example:
```bash
npm myfile.js
```

With `ts-node` (combining compiling and running):
```bash
ts-node myfile.ts
```

To see the full list of available options for `tsc` run:
```bash
tsc -help
```

Initialization (setting up template project)
```bash
tsc --init
```
This will create `tsconfig.json` having variety of config settings

---
- [Home](https://heartthymes.github.io)