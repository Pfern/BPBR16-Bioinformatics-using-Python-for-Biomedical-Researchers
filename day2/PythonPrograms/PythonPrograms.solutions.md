#### Solution to challenge #2

```
a = raw_input("Type something: ")
print a
```
<a href="https://github.com/Pfern/BPBR16-Bioinformatics-using-Python-for-Biomedical-Researchers/blob/master/day2/PythonPrograms/PythonPrograms.md#challenge-2>back<a/>



#### Solution to challenge #4
```
dna = "AGCTTCGA"

print dna.count("A")
print dna.count("C")
print dna.count("T")
print dna.count("G")
```
<a href="https://github.com/Pfern/BPBR16-Bioinformatics-using-Python-for-Biomedical-Researchers/blob/master/day2/PythonPrograms/PythonPrograms.md#challenge-4>back<a/>


#### Solution to challenge #5
```
telomerase = open("telomerase.txt")

seq = telomerase.read()

print seq

for aa in seq:
  print aa
```
<a href="https://github.com/Pfern/BPBR16-Bioinformatics-using-Python-for-Biomedical-Researchers/blob/master/day2/PythonPrograms/PythonPrograms.md#challenge-5>back<a/>


#### Solution to challenge #6
```
telomerase = open("telomerase.txt")

for line in telomerase:
  print line
```
<a href="https://github.com/Pfern/BPBR16-Bioinformatics-using-Python-for-Biomedical-Researchers/blob/master/day2/PythonPrograms/PythonPrograms.md#challenge-6>back<a/>


#### Solution to challenge #7
```
telomerase = open("telomerase.txt")

seq = telomerase.read()

for aa in "ACDEFGHKILMNPQRSTVYW":
  aa_count = seq.count(aa)
  aa_freq = aa_count/float(len(seq))
  print aa, round(aa_freq, 3)
```
<a href="https://github.com/Pfern/BPBR16-Bioinformatics-using-Python-for-Biomedical-Researchers/blob/master/day2/PythonPrograms/PythonPrograms.md#challenge-7>back<a/>
