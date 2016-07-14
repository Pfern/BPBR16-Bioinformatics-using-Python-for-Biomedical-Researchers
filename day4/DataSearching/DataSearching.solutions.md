
#### Solution to challenge #1

```
F = open('rna_seq.fasta')
Out = open('protein_seq.fasta','w')

for line in F:
    if line[0] == '>':
        header = line.split()
        geneID = header[0]
        Out.write(geneID + '_protein\n')
    else:
        seq = seq + line.strip()

from tgac import codonAMINO
prot = ''
for i in range(0,len(seq),3):
    if codonAMINO.has_key(seq[i:i+3]):
        prot = prot + codonAMINO[seq[i:i+3]]
    else:
        prot = prot + '*'

Out.write(prot + '\n')
```



#### Solution to challenge #2
```
from tgac import codonAMINO

prot = ''
for j in range(3):
    Out.write(str(j) + "-frame\n")
    for i in range(j,len(seq),3):
        if codonAMINO.has_key(seq[i:i+3]):
            prot = prot + codonAMINO[seq[i:i+3]]
        else:
            prot = prot + '*'

    Out.write(prot + '\n')
prot = ''
```
