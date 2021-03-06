# Overview

PyScanner is a Java-like input scanner.

This is very useful for reading input for programming contests such as ACM ICPC, Topcoder, Google Code Jam, and Facebook Hacker Cup.

# Installation

    easy_install3 PyScanner

And then in your python3 module include:

    from scanner import Scanner

# Examples

The following example allows to read a float from stdin:
```python
# Input:
# 3 0.5
sc = Scanner()
x = sc.next_int()
y = sc.next_float()
type(x) is int # True
type(y) is float # True
x + y # 3.5
```

The following code allows to read until EOF and obtain int types:
```python
# Assume input is:
# 10 20 30
# 40 50 60
sc = Scanner()
sum = 0
while sc.has_next():
    sum += sc.next_int()
sum # 210
```

The default input stream is sys.stdin. However, it is possible to read from a file or even a string:
```python
sc = Scanner(file='data.txt')
# do stuff
sc.close()
```

```python
sc = Scanner(source='some string to use as input')
```

The scanner can also use string delimeters other than whitespace.
```python
sc = Scanner(delim=',')
```

By default, the scanner does a str split. If forced, a regex pattern can also be used. As expected, the latter method is slower:
```python
content = '1 fish  2.5 fish red fish  blue fish
sc = Scanner(source=content, delim='\S*fish\S*', force_regex=True)
sc.next_int() # 1
sc.has_next() # True
sc.next_float() # 2.5
sc.next() # red
sc.next() # blue
sc.has_next() # False
```

# Usage
TODO: example using the Scanner vs. standard Python way.

# License

[THE BEER-WARE LICENSE](https://tldrlegal.com/license/beerware-license)
    
