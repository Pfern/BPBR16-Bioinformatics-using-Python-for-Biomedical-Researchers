# Python programs

## How can I run a program?
### Input and output

In this module you can learn
-  How to read, process, and output text
-  How to read from the keyboard
-  How to write to the screen
-  How to repeat things
-  How to create your own modules

<img src="../../img/pp1.png" alt="slot" style="width: 100px;"/>


## What is a program?
It is a text file that contains Python commands or, in other words, lines of code


> ####  **Challenge #1**
---
>•  Open a text file, write: <br>
>print `"This is the output of my first program"`
>•  save the file with the name my_print.py and exit
>•  Open a terminal, go to the directory where you saved `my_print.py` and type at the cursor:
> `python my_print.py`

<img src="../../img/pp2.png" alt="slot" style="width: 100px;"/>

<img src="../../img/pp3.png" alt="slot" style="width: 100px;"/>
## Input
<img src="../../img/pp4.png" alt="slot" style="width: 100px;"/>


## Input from the program itself
```
a = 3
print a
```

## Input from the keyboard
```
>>> a = raw_input("Type a number: ")
Type a number: 3
>>> print a
3
```

> ####  **Challenge #2**
---
>Write a program that reads something from the keyboard and print it to the screen.
>
---

See the <a href="https://github.com/Pfern/BPBR16-Bioinformatics-using-Python-for-Biomedical-Researchers/blob/master/day2/PythonPrograms/PythonPrograms.solutions.md#solution-to-challenge-2">solution to challenge #2<a/>



## Input from a text file
-  We need to “access” an existing input file
-  And read its content

```
Infile = open("insulin.txt")

content = Infile.read()

print content
```

## From a Python module
-  A Python module is a text file (with the `.py` extension) that contains (Python) definitions/assignments
-   Python modules can be accessed from programs using the import statement


#### Python module insulin.py
```
insulin = "GIVEQCCTSICSLYQLENYCNFVNQHLCGSHL\
VEALYLVCGERGFFYTPKT"
```
#### Python program my_first_import.py
```
from insulin import insulin
print insulin
```
> ####  **Challenge #3**
---
>Write a program that reads a sequence from a file and print it to the screen. Run it.
>
---

## Output

<img src="../../img/pp5.png" alt="slot" style="width: 100px;"/>


## To the computer screen
Which command we use?


## To a text file
-  We need to “open” a text file in the “writing”
mode
-  We have to write to it.

```
from insulin import insulin

outfile = open("my_output.txt", "w")
outfile.write(insulin)
outfile.close()
```
<img src="../../img/pp6.png" alt="slot" style="width: 100px;"/>




> ####  **Challenge #4**
---
>Calculate DNA base occurrences
>
>Write a program that counts how many times the four bases occur in a DNA sequence. The program should:
>-  Store the DNA sequence in a variable.
>-  Count how often each base occurs.
>-  Write all four numbers to the screen.
>Test it with a DNA sequence for which you know the result, for instance “AAAACCCGGT”. This approach makes it much easier to discover small program errors.
>
----

See the <a href="https://github.com/Pfern/BPBR16-Bioinformatics-using-Python-for-Biomedical-Researchers/blob/master/day2/PythonPrograms/PythonPrograms.solutions.md#solution-to-challenge-4">solution to challenge #4<a/>




## Counting amino acids
<img src="../../img/pp7.png" alt="slot" style="width: 100px;"/>

```
# insulin [Homo sapiens] GI:386828
insulin = "GIVEQCCTSICSLYQLENYCFVNQHLC\
      GSHLVEALYLVGERGFFYTPKT"

for amino_acid in "ACDEFGHIKLMNPQRSTVWY"
  number = insulin.count(amino_acid)
  print amino_acid, number
```

##Loops with for
The `for` command repeats other commands:
```
dna = "AGCTTCGA”

for base in "ACTG":
  print dna.count(base)
```

The commands that are repeated must be **indented (shifted right by four spaces)**.


## Compare
```
dna = "AGCTTCGA”
for base in "ACTG":
  print dna.count(base)
```
Would you prefer this implementation?
```
dna = "AGCTTCGA"

print dna.count("A")
print dna.count("C")
print dna.count("T")
print dna.count("G")
```
Why or why not?

> ####  **Challenge #5**
---
>Retrieve the 1132-residue sequence of human telomerase reverse transcriptase isoform 1 from the NCBI protein database. Choose the FASTA format. Copy the sequence to a text file (`telomerase.txt`). Write a program that reads the telomerase.txt file and prints first the whole sequence and then the sequence residue by residue.
>
----


See the <a href="https://github.com/Pfern/BPBR16-Bioinformatics-using-Python-for-Biomedical-Researchers/blob/master/day2/PythonPrograms/PythonPrograms.solutions.md#solution-to-challenge-5">solution to challenge #5<a/>


## You can use a `for` loop to read a file line by line
```
Input_file = open(“my_file.txt”)
for line in Input_file:
  print line
```

## Look how beautiful it can be…
```
import urllib
url = 'http://www.uniprot.org/\
  uniprot/P12931.fasta'
src_human = urllib.urlopen(url)
for line in src_human:
  print line,
```


> ####  **Challenge #6**
---
> Write a file and program that reads the `telomerase.txt` prints its content line by line.
>
---

See the <a href="https://github.com/Pfern/BPBR16-Bioinformatics-using-Python-for-Biomedical-Researchers/blob/master/day2/PythonPrograms/PythonPrograms.solutions.md#solution-to-challenge-6">solution to challenge #6<a/>


<img src="../../img/pp8.png" alt="slot" style="width: 100px;"/>


> ####  **Challenge #7**
---
> Which amino acid is the most frequent in the sequence of the telomerase reverse transcriptase isoform 1?
>
---


See the <a href="https://github.com/Pfern/BPBR16-Bioinformatics-using-Python-for-Biomedical-Researchers/blob/master/day2/PythonPrograms/PythonPrograms.solutions.md#solution-to-challenge-7">solution to challenge #7<a/>


## Recap
### Recap I
-  string variables contain text
-  `print` writes to the screen
-  you can use functions to do things
-  you can enter text with `raw_input()`    
-  `write()` writes to an open file
-  for loops repeat commands
-  comments starts with `#` or `'''`

### Recap II
<img src="../../img/pp9.png" alt="slot" style="width: 100px;"/>
