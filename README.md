# Unix_Assignment_AYL
The respiratory for BCB 546X Unix_Assignment

# Pipeline
1. 
2. 
3. 
4. 
5. 

# Commandlines
- awk '{print $1 "\t" $3 "\t" $4}' snp_position.txt > File01.txt
- grep "Sample_ID" fang_et_al_genotypes.txt > File02.txt
- cut -d $'\t' -f 1,3- fang_et_al_genotypes.txt > File03.txt
- awk '{
       for (f = 1; f <= NF; f++) { a[NR, f] = $f }
     }
     NF > nf { nf = NF }
     END {
       for (f = 1; f <= nf; f++) {
           for (r = 1; r <= NR; r++) {
               printf a[r, f] (r==NR ? RS : FS)
           }
       }
    }' File03.txt > File04.txt
