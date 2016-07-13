#### Solution to challenge #1

```
def triangle_area(b, h):
    A = (b*h)/2.0 # function  body
    return A      # function  body

print triangle_area(2.28, 3.55)
```

```
def triangle_area(b, h):
    return (b*h)/2.0

print triangle_area(2.28, 3.55)
```

#### Solution to challenge #2

```
def get_values(arg1, arg2):
    s = arg1 + arg2
    d = arg1 - arg2
    p = arg1 * arg2
    return s, d, p

print get_values(15, 8)
```



#### Solution to challenge #3

```
import math

def distance(p1, p2):
    dist = math.sqrt((p1[0]-p2[0])**2 +
                     (p1[1]-p2[1])**2 +
                     (p1[2]-p2[2])**2)
    return dist

p1 = (43.64, 30.72, 88.95)
p2 = (45.83, 31.11, 92.04)

print "Distance:", distance(p1, p2)
```

#### Solution to challenge #4

```
def return_header(filename):
    fasta = open(filename)
    for line in fasta:
      if line[0] == '>':
        return line

print return_header('SingleSeq.fasta')
```


#### Solution to challenge #5
```
def return_header(filename):
    fasta = open(filename)
    for line in fasta:
        if line[0] == '>':
            return line

filenames = ['SingleSeq1.fasta',
              'SingleSeq2.fasta',
              'SingleSeq3.fasta']

for name in filenames:
    print return_header(name)
```

#### Solution to challenge #6
one possible solution
```
def return_header(filename):
    fasta = open(filename)
    for line in fasta:
        if line[0] == '>':
            return line

filenames = ['SingleSeq1.fasta',
             'SingleSeq2.fasta',
             'SingleSeq3.fasta']

output = open("headers.txt", "w")

for name in filenames:
    output.write(return_header(name) + '\n')

output.close()
```
another possible solution

```
def return_header(filename):
    fasta = open(filename)
    for line in fasta:
        if line[0] == '>':
          return line

filenames = ['SingleSeq1.fasta',
             'SingleSeq2.fasta',
             'SingleSeq3.fasta']
n = 0
for name in filenames:
    n = n + 1
    output = open("header" + str(n) + ".txt", "w")
    output.write(return_header(name))

output.close()
```

#### Solution to challenge #7

```
def genbank2fasta(filename):
    name = filename.split('.')[0]
    InputFile = open(filename)
    OutputFile = open(name + ".fasta","w")
    flag = 0
    for line in InputFile:
        if line[0:9] == 'ACCESSION':
            AC = line.split()[1].strip()
            OutputFile.write('>'+AC+'\n')
        if line[0:6] == 'ORIGIN':
            flag = 1
            continue
        if flag == 1:
            fields = line.split()
            if fields != []:
                seq = ''.join(fields[1:])
                OutputFile.write(seq +'\n')
OutputFile.close()

filename = "ap006852.gbk"
genbank2fasta(filename)
```

## General remarks

-  Python uses **dynamical** namespaces: when a function is
called, *its namespace is automatically created*

- The variables defined in the body of a function live in its *local* namespace and not in the script (or module) *global* namespace

- Local objects can be made global using the **global** statement

- When a function is called, names of the objects used in its body
are first searched in the function namespace and subsequently,
if they are not found in the function body, they are searched in
the script (module) global namespace.

```
>>> def f():
...     x = 100
...     return x
...
>>> print x
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
NameError: name 'x' is not defined
>>> f()
100
>>> print x
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
NameError: name 'x' is not defined
>>>
```
`x` is a local name of the function `f()` namespace and it is not
recognised by the `print` statement in the main script  even
after the function call

```
>>> def g():
...     global x
...     x = 200
...     return x
...
>>> print x
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
NameError: name 'x' is not defined
>>> g()
200
>>> print x
200
>>>
```

The variable `x`, defined in the body of the `g()` function, is made
global using the **global** statement but is recognised by the
`print` statement in the main script  only after the function call

```
>>> y = "ACCTGGCACAA"
>>> def h():
...     print y
...
>>> h()
'ACCTGGCACAA'
```

`y` is recognized when `h()` is called as it is a global name.
The  number  of  arguments  can  be  variable  (i.e.  can  change  from  one function call to the other); in this case, you can use * or ** symbols.

1st  case             (\*args) =>          tuple of arguments
2nd  case             (\**args)=>          dictionary of arguments

```
>>> def print_args(\*args):
...     print args
...     return
...
>>> print_args(1,2,3,4,5)
(1, 2, 3, 4, 5)
>>> print_args("Hello world!")
(‘Hello world!’,)
>>> print_args(100, 200, "ACCTGGCACAA")
(100, 200, ‘ACCTGGCACAA’)
>>> def print_args2(**args):
...     print args
...     return
...
>>>  print_args2(num  =  100,  num2  =  200, seq  =
"ACCTGGCACAA")
{'num': 100, 'seq': 'ACCTGGCACAA', 'num2': 200}
```
