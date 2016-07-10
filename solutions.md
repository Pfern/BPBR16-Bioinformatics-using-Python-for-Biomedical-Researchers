#### Program 1 - solution

```
seq = open("SingleSeq.fasta")

for line in seq:
print line
```

<a href="#delivering"></a>
#### Program 2 - solution

```
seq = open("SingleSeq.fasta")
seq_2 = open("SingleSeq-2.fasta","w")

for line in seq:
seq_2.write(line)

seq_2.close()
```
