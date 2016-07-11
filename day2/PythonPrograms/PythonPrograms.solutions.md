#### Solution to challenge #2

```
a = raw_input("Type something: ")
print a
```

#### Solution to challenge #4
```
dna = "AGCTTCGA"

print dna.count("A")
print dna.count("C")
print dna.count("T")
print dna.count("G")
```

#### Solution to challenge #5
```
telomerase = open("telomerase.txt")

seq = telomerase.read()

print seq

for aa in seq:
  print aa
```

#### Solution to challenge #6
```
telomerase = open("telomerase.txt")

for line in telomerase:
  print line
```

#### Solution to challenge #7
```
telomerase = open("telomerase.txt")

seq = telomerase.read()

for aa in "ACDEFGHKILMNPQRSTVYW":
  aa_count = seq.count(aa)
  aa_freq = aa_count/float(len(seq))
  print aa, round(aa_freq, 3)
