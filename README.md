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
- awk -F $'\t' '{
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
- grep "ZMMIL\|ZMMLR\|ZMMMR" fang_et_al_genotypes.txt >> File02.txt


- cat File02.txt > Group01.txt | grep "ZMMIL\|ZMMLR\|ZMMMR" fang_et_al_genotypes.txt >> Group01.txt
- cut -d $'\t' -f 1,3- Group01.txt > Group01_2.txt
- awk -F $'\t' '{
       for (f = 1; f <= NF; f++) { a[NR, f] = $f }
     }
     NF > nf { nf = NF }
     END {
       for (f = 1; f <= nf; f++) {
           for (r = 1; r <= NR; r++) {
               printf a[r, f] (r==NR ? RS : FS)
           }
       }
    }' Group01_2.txt > Group01_3.txt

**sed -i '/Group/d' Group01_3.txt**
join -t $'\t' File01.txt Group01_3.txt > Group01_4.txt

- sed -e "${grep 'Sample_ID'}r Group01_3.txt" File01

- grep "Sample_ID" Group01_3.txt >> 
    
    
 - sed 's/^SNP_ID/ s/$/' filename
sed '/Fred Flintstone/ s/$/ ***/' filename

sed 's/^Fred.*/& ***/' filename
- join 
