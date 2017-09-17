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
- awk '{print $1 "\t" $3 "\t" $4}' snp_position.txt | grep 'SNP_ID' > File05.txt
- grep 'Sample_ID' Group01_3.txt | cut -d $'\t' -f 2- > File06.txt
- paste File05.txt File06.txt > File07.txt

- sed -i '/Group/d;/Sample_ID/d' Group01_3.txt
- sed -i '/SNP_ID/d' File01.txt
- sort -t $'\t' -k1 File01.txt > File01_1.txt
- sort -t $'\t' -k1 Group01_3.txt > Group01_4.txt
- join -t $'\t' File01_1.txt Group01_4.txt > Group01_5.txt
- mkdir ZM/
- mkdir Position_multip_unknown
cat Group01_5.txt | awk '$2 == "1"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_1.txt
cat Group01_5.txt | awk '$2 == "2"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_2.txt
cat Group01_5.txt | awk '$2 == "3"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_3.txt
cat Group01_5.txt | awk '$2 == "4"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_4.txt
cat Group01_5.txt | awk '$2 == "5"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_5.txt
cat Group01_5.txt | awk '$2 == "6"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_6.txt
cat Group01_5.txt | awk '$2 == "7"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_7.txt
cat Group01_5.txt | awk '$2 == "8"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_8.txt
cat Group01_5.txt | awk '$2 == "9"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_9.txt
cat Group01_5.txt | awk '$2 == "10"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_10.txt

cat Group01_5.txt | awk '$2 == "1"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_1.txt
cat Group01_5.txt | awk '$2 == "2"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_2.txt
cat Group01_5.txt | awk '$2 == "3"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_3.txt
cat Group01_5.txt | awk '$2 == "4"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_4.txt
cat Group01_5.txt | awk '$2 == "5"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_5.txt
cat Group01_5.txt | awk '$2 == "6"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_6.txt
cat Group01_5.txt | awk '$2 == "7"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_7.txt
cat Group01_5.txt | awk '$2 == "8"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_8.txt
cat Group01_5.txt | awk '$2 == "9"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_9.txt
cat Group01_5.txt | awk '$2 == "10"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_10.txt

cat Group01_5.txt | awk '$3 == "unknown"' > ./Position_multip_unknown/position_unknown.txt
cat Group01_5.txt | awk '$2 == "multiple"||$3 == "multiple"' > ./Position_multip_unknown/nultiple_position.txt

cat File07.txt >> ./ZM_Ascending/Chr01_Ascend.txt | cat ./ZM_Ascending/chromosome_1.txt >> ./ZM_Ascending/Chr01_Ascend.txt



- mv ./ZM ./ZM_Ascending
- cp -r ./ZM_Ascending ./ZM_Descending
- 










- **cat Group01_5.txt >> File07.txt** 
awk '$3 == "rahmu"'

awk -F $'\t' '{
       for (f = 1; f <= 10; f++) {
           if ($2 == f) print $0;}
  
awk -F $'\t' '{for (f = 1; f <= NF; f++) { if ($2 == f) print $0;}}' Group01_5.txt > ZM_Chromosome-$(f = 1; f <= NF; f++).txt

awk -F $'\t' '{
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














- join -t $'\t' Group01_3.txt > Group01_4.txt

- sed -e "${grep 'Sample_ID'}r Group01_3.txt" File01

- grep "Sample_ID" Group01_3.txt >> 
    
    
 - sed 's/^SNP_ID/ s/$/' filename
sed '/Fred Flintstone/ s/$/ ***/' filename

sed 's/^Fred.*/& ***/' filename
- join 
