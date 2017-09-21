# Unix_Assignment_AYL
The respiratory for BCB 546X Unix_Assignment


# Commandlines for Maize
## Basic data processing
- awk '{print $1 "\t" $3 "\t" $4}' snp_position.txt > File01.txt **#SNP_ID and position**
- grep "Sample_ID" fang_et_al_genotypes.txt > File02.txt  **#Sample_ID and location**
- cat File02.txt >> Group01.txt | grep "ZMMIL\|ZMMLR\|ZMMMR" fang_et_al_genotypes.txt >> Group01.txt **#Grep All ZM samples**
- cut -d $'\t' -f 1,3- Group01.txt > Group01_2.txt **#SampleID, Group, sequence**
- awk -F $'\t' '{for (f = 1; f <= NF; f++) { a[NR, f] = $f }} NF > nf { nf = NF } END {for (f = 1; f <= nf; f++) {for (r = 1; r <= NR; r++) {printf a[r, f] (r==NR ? RS : FS)}}}' Group01_2.txt > Group01_3.txt **#Transpose**
- awk '{print $1 "\t" $3 "\t" $4}' snp_position.txt | grep 'SNP_ID' > File05.txt **#Header for SNP_ID, Chromosome Position**
- grep 'Sample_ID' Group01_3.txt | cut -d $'\t' -f 2- > File06.txt **#Header for Sample_ID**
- paste File05.txt File06.txt > File07.txt **#Total Header**
- sort -t $'\t' -k1 File01.txt > File01_1.txt
- sort -t $'\t' -k1 Group01_3.txt > Group01_4.txt **#sort before join**
- join -t $'\t' File01_1.txt Group01_4.txt > Group01_5.txt **#join together**
- mkdir ZM_Ascending/ ZM_Descending/ Position_multip_unknown/

## Seperate the data by chomoromse and then sort the data by position
### Ascending
- cat Group01_5.txt | awk '$2 == "1"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_1.txt
- cat Group01_5.txt | awk '$2 == "2"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_2.txt
- cat Group01_5.txt | awk '$2 == "3"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_3.txt
- cat Group01_5.txt | awk '$2 == "4"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_4.txt
- cat Group01_5.txt | awk '$2 == "5"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_5.txt
- cat Group01_5.txt | awk '$2 == "6"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_6.txt
- cat Group01_5.txt | awk '$2 == "7"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_7.txt
- cat Group01_5.txt | awk '$2 == "8"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_8.txt
- cat Group01_5.txt | awk '$2 == "9"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_9.txt
- cat Group01_5.txt | awk '$2 == "10"' | sort -n -k3,3 > ./ZM_Ascending/chromosome_10.txt
### Descending
- cat Group01_5.txt | awk '$2 == "1"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_1.txt
- cat Group01_5.txt | awk '$2 == "2"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_2.txt
- cat Group01_5.txt | awk '$2 == "3"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_3.txt
- cat Group01_5.txt | awk '$2 == "4"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_4.txt
- cat Group01_5.txt | awk '$2 == "5"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_5.txt
- cat Group01_5.txt | awk '$2 == "6"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_6.txt
- cat Group01_5.txt | awk '$2 == "7"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_7.txt
- cat Group01_5.txt | awk '$2 == "8"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_8.txt
- cat Group01_5.txt | awk '$2 == "9"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_9.txt
- cat Group01_.txt | awk '$2 == "10"' | sort -rn -k3,3 > ./ZM_Descending/chromosome_10.txt
### Position unknown/multiple positions
- cat Group01_5.txt | awk '$3 == "unknown"' > ./Position_multip_unknown/position_unknown.txt
- cat Group01_5.txt | awk '$2 == "multiple"||$3 == "multiple"' > ./Position_multip_unknown/nultiple_position.txt

## Add Header to the files
- cat File07.txt >> ./ZM_Ascending/Chr01_Ascend.txt | cat ./ZM_Ascending/chromosome_1.txt >> ./ZM_Ascending/Chr01_Ascend.txt
- cat File07.txt >> ./ZM_Ascending/Chr02_Ascend.txt | cat ./ZM_Ascending/chromosome_2.txt >> ./ZM_Ascending/Chr02_Ascend.txt
- cat File07.txt >> ./ZM_Ascending/Chr03_Ascend.txt | cat ./ZM_Ascending/chromosome_3.txt >> ./ZM_Ascending/Chr03_Ascend.txt
- cat File07.txt >> ./ZM_Ascending/Chr04_Ascend.txt | cat ./ZM_Ascending/chromosome_4.txt >> ./ZM_Ascending/Chr04_Ascend.txt
- cat File07.txt >> ./ZM_Ascending/Chr05_Ascend.txt | cat ./ZM_Ascending/chromosome_5.txt >> ./ZM_Ascending/Chr05_Ascend.txt
- cat File07.txt >> ./ZM_Ascending/Chr06_Ascend.txt | cat ./ZM_Ascending/chromosome_6.txt >> ./ZM_Ascending/Chr06_Ascend.txt
- cat File07.txt >> ./ZM_Ascending/Chr07_Ascend.txt | cat ./ZM_Ascending/chromosome_7.txt >> ./ZM_Ascending/Chr07_Ascend.txt
- cat File07.txt >> ./ZM_Ascending/Chr08_Ascend.txt | cat ./ZM_Ascending/chromosome_8.txt >> ./ZM_Ascending/Chr08_Ascend.txt
- cat File07.txt >> ./ZM_Ascending/Chr09_Ascend.txt | cat ./ZM_Ascending/chromosome_9.txt >> ./ZM_Ascending/Chr09_Ascend.txt
- cat File07.txt >> ./ZM_Ascending/Chr10_Ascend.txt | cat ./ZM_Ascending/chromosome_10.txt >> ./ZM_Ascending/Chr10_Ascend.txt

- cat File07.txt >> ./ZM_Descending/Chr01_Descend.txt | cat ./ZM_Descending/chromosome_1.txt >> ./ZM_Descending/Chr01_Descend.txt
- cat File07.txt >> ./ZM_Descending/Chr02_Descend.txt | cat ./ZM_Descending/chromosome_2.txt >> ./ZM_Descending/Chr02_Descend.txt
- cat File07.txt >> ./ZM_Descending/Chr03_Descend.txt | cat ./ZM_Descending/chromosome_3.txt >> ./ZM_Descending/Chr03_Descend.txt
- cat File07.txt >> ./ZM_Descending/Chr04_Descend.txt | cat ./ZM_Descending/chromosome_4.txt >> ./ZM_Descending/Chr04_Descend.txt
- cat File07.txt >> ./ZM_Descending/Chr05_Descend.txt | cat ./ZM_Descending/chromosome_5.txt >> ./ZM_Descending/Chr05_Descend.txt
- cat File07.txt >> ./ZM_Descending/Chr06_Descend.txt | cat ./ZM_Descending/chromosome_6.txt >> ./ZM_Descending/Chr06_Descend.txt
- cat File07.txt >> ./ZM_Descending/Chr07_Descend.txt | cat ./ZM_Descending/chromosome_7.txt >> ./ZM_Descending/Chr07_Descend.txt
- cat File07.txt >> ./ZM_Descending/Chr08_Descend.txt | cat ./ZM_Descending/chromosome_8.txt >> ./ZM_Descending/Chr08_Descend.txt
- cat File07.txt >> ./ZM_Descending/Chr09_Descend.txt | cat ./ZM_Descending/chromosome_9.txt >> ./ZM_Descending/Chr09_Descend.txt
- cat File07.txt >> ./ZM_Descending/Chr10_Descend.txt | cat ./ZM_Descending/chromosome_10.txt >> ./ZM_Descending/Chr10_Descend.txt
- sed 's/?\/?/-\/-/g' ./ZM_Descending/Chr*

- cat File07.txt >> ./Position_multip_unknown/Position_Unknown.txt | cat ./Position_multip_unknown/position_unknown.txt >> ./Position_multip_unknown/Position_Unknown.txt
- cat File07.txt >> ./Position_multip_unknown/Multiple_Position.txt | cat ./Position_multip_unknown/multiple_position.txt >> ./Position_multip_unknown/Multiple_Position.txt


# Commandlines for Teosnite
## Basic data processing
- awk '{print $1 "\t" $3 "\t" $4}' snp_position.txt > File01.txt **#SNP_ID and position**
- grep "Sample_ID" fang_et_al_genotypes.txt > File02.txt  **#Sample_ID and location**
- cat File02.txt >> Group01.txt | grep "ZMPBA\|ZMPIL\|ZMPJA" fang_et_al_genotypes.txt >> Group01.txt **#Grep All ZM samples**
- cut -d $'\t' -f 1,3- Group01.txt > Group01_2.txt **#SampleID, Group, sequence**
- awk -F $'\t' '{for (f = 1; f <= NF; f++) { a[NR, f] = $f }} NF > nf { nf = NF } END {for (f = 1; f <= nf; f++) {for (r = 1; r <= NR; r++) { printf a[r, f] (r==NR ? RS : FS) }}}' Group01_2.txt > Group01_3.txt **#Transpose**
- awk '{print $1 "\t" $3 "\t" $4}' snp_position.txt | grep 'SNP_ID' > File05.txt **#Header for SNP_ID, Chromosome Position**
- grep 'Sample_ID' Group01_3.txt | cut -d $'\t' -f 2- > File06.txt **#Header for Sample_ID**
- paste File05.txt File06.txt > File07.txt **#Total Header**
- sort -t $'\t' -k1 File01.txt > File01_1.txt
- sort -t $'\t' -k1 Group01_3.txt > Group01_4.txt **#sort before join**
- join -t $'\t' File01_1.txt Group01_4.txt > Group01_5.txt **#join together**
- mkdir Teo_Ascending/ Teo_Descending/ Teo_Position_multip_unknown/

## Seperate the data by chomoromse and then sort the data by position
### Ascending
- cat Group01_5.txt | awk '$2 == "1"' | sort -n -k3,3 > ./Teo_Ascending/chromosome_1.txt
- cat Group01_5.txt | awk '$2 == "2"' | sort -n -k3,3 > ./Teo_Ascending/chromosome_2.txt
- cat Group01_5.txt | awk '$2 == "3"' | sort -n -k3,3 > ./Teo_Ascending/chromosome_3.txt
- cat Group01_5.txt | awk '$2 == "4"' | sort -n -k3,3 > ./Teo_Ascending/chromosome_4.txt
- cat Group01_5.txt | awk '$2 == "5"' | sort -n -k3,3 > ./Teo_Ascending/chromosome_5.txt
- cat Group01_5.txt | awk '$2 == "6"' | sort -n -k3,3 > ./Teo_Ascending/chromosome_6.txt
- cat Group01_5.txt | awk '$2 == "7"' | sort -n -k3,3 > ./Teo_Ascending/chromosome_7.txt
- cat Group01_5.txt | awk '$2 == "8"' | sort -n -k3,3 > ./Teo_Ascending/chromosome_8.txt
- cat Group01_5.txt | awk '$2 == "9"' | sort -n -k3,3 > ./Teo_Ascending/chromosome_9.txt
- cat Group01_5.txt | awk '$2 == "10"' | sort -n -k3,3 > ./Teo_Ascending/chromosome_10.txt
### Descending
- cat Group01_5.txt | awk '$2 == "1"' | sort -rn -k3,3 > ./Teo_Descending/chromosome_1.txt
- cat Group01_5.txt | awk '$2 == "2"' | sort -rn -k3,3 > ./Teo_Descending/chromosome_2.txt
- cat Group01_5.txt | awk '$2 == "3"' | sort -rn -k3,3 > ./Teo_Descending/chromosome_3.txt
- cat Group01_5.txt | awk '$2 == "4"' | sort -rn -k3,3 > ./Teo_Descending/chromosome_4.txt
- cat Group01_5.txt | awk '$2 == "5"' | sort -rn -k3,3 > ./Teo_Descending/chromosome_5.txt
- cat Group01_5.txt | awk '$2 == "6"' | sort -rn -k3,3 > ./Teo_Descending/chromosome_6.txt
- cat Group01_5.txt | awk '$2 == "7"' | sort -rn -k3,3 > ./Teo_Descending/chromosome_7.txt
- cat Group01_5.txt | awk '$2 == "8"' | sort -rn -k3,3 > ./Teo_Descending/chromosome_8.txt
- cat Group01_5.txt | awk '$2 == "9"' | sort -rn -k3,3 > ./Teo_Descending/chromosome_9.txt
- cat Group01_5.txt | awk '$2 == "10"' | sort -rn -k3,3 > ./Teo_Descending/chromosome_10.txt
### Position unknown/Multiple positions
- cat Group01_5.txt | awk '$3 == "unknown"' > ./Teo_Position_multip_unknown/position_unknown.txt
- cat Group01_5.txt | awk '$2 == "multiple"||$3 == "multiple"' > ./Teo_Position_multip_unknown/multiple_position.txt

## Add Header to the files
- cat File07.txt >> ./Teo_Ascending/Chr01_Ascend.txt | cat ./Teo_Ascending/chromosome_1.txt >> ./Teo_Ascending/Chr01_Ascend.txt
- cat File07.txt >> ./Teo_Ascending/Chr02_Ascend.txt | cat ./Teo_Ascending/chromosome_2.txt >> ./Teo_Ascending/Chr02_Ascend.txt
- cat File07.txt >> ./Teo_Ascending/Chr03_Ascend.txt | cat ./Teo_Ascending/chromosome_3.txt >> ./Teo_Ascending/Chr03_Ascend.txt
- cat File07.txt >> ./Teo_Ascending/Chr04_Ascend.txt | cat ./Teo_Ascending/chromosome_4.txt >> ./Teo_Ascending/Chr04_Ascend.txt
- cat File07.txt >> ./Teo_Ascending/Chr05_Ascend.txt | cat ./Teo_Ascending/chromosome_5.txt >> ./Teo_Ascending/Chr05_Ascend.txt
- cat File07.txt >> ./Teo_Ascending/Chr06_Ascend.txt | cat ./Teo_Ascending/chromosome_6.txt >> ./Teo_Ascending/Chr06_Ascend.txt
- cat File07.txt >> ./Teo_Ascending/Chr07_Ascend.txt | cat ./Teo_Ascending/chromosome_7.txt >> ./Teo_Ascending/Chr07_Ascend.txt
- cat File07.txt >> ./Teo_Ascending/Chr08_Ascend.txt | cat ./Teo_Ascending/chromosome_8.txt >> ./Teo_Ascending/Chr08_Ascend.txt
- cat File07.txt >> ./Teo_Ascending/Chr09_Ascend.txt | cat ./Teo_Ascending/chromosome_9.txt >> ./Teo_Ascending/Chr09_Ascend.txt
- cat File07.txt >> ./Teo_Ascending/Chr10_Ascend.txt | cat ./Teo_Ascending/chromosome_10.txt >> ./Teo_Ascending/Chr10_Ascend.txt

- cat File07.txt >> ./Teo_Descending/Chr01_Descend.txt | cat ./Teo_Descending/chromosome_1.txt >> ./Teo_Descending/Chr01_Descend.txt
- cat File07.txt >> ./Teo_Descending/Chr02_Descend.txt | cat ./Teo_Descending/chromosome_2.txt >> ./Teo_Descending/Chr02_Descend.txt
- cat File07.txt >> ./Teo_Descending/Chr03_Descend.txt | cat ./Teo_Descending/chromosome_3.txt >> ./Teo_Descending/Chr03_Descend.txt
- cat File07.txt >> ./Teo_Descending/Chr04_Descend.txt | cat ./Teo_Descending/chromosome_4.txt >> ./Teo_Descending/Chr04_Descend.txt
- cat File07.txt >> ./Teo_Descending/Chr05_Descend.txt | cat ./Teo_Descending/chromosome_5.txt >> ./Teo_Descending/Chr05_Descend.txt
- cat File07.txt >> ./Teo_Descending/Chr06_Descend.txt | cat ./Teo_Descending/chromosome_6.txt >> ./Teo_Descending/Chr06_Descend.txt
- cat File07.txt >> ./Teo_Descending/Chr07_Descend.txt | cat ./Teo_Descending/chromosome_7.txt >> ./Teo_Descending/Chr07_Descend.txt
- cat File07.txt >> ./Teo_Descending/Chr08_Descend.txt | cat ./Teo_Descending/chromosome_8.txt >> ./Teo_Descending/Chr08_Descend.txt
- cat File07.txt >> ./Teo_Descending/Chr09_Descend.txt | cat ./Teo_Descending/chromosome_9.txt >> ./Teo_Descending/Chr09_Descend.txt
- cat File07.txt >> ./Teo_Descending/Chr10_Descend.txt | cat ./Teo_Descending/chromosome_10.txt >> ./Teo_Descending/Chr10_Descend.txt
- sed 's/?\/?/-\/-/g' ./Teo_Descending/Chr*

- cat File07.txt >> ./Teo_Position_multip_unknown/Position_Unknown.txt | cat ./Teo_Position_multip_unknown/position_unknown.txt >> ./Teo_Position_multip_unknown/Position_Unknown.txt
- cat File07.txt >> ./Teo_Position_multip_unknown/Multiple_Position.txt | cat ./Teo_Position_multip_unknown/multiple_position.txt >> ./Teo_Position_multip_unknown/Multiple_Position.txt





