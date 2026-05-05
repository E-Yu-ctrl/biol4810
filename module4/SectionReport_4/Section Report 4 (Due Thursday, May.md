### **Section Report 4 (Due Thursday, May 14)**



1. Check the quality of the raw reads

   1. Tool: Falco *(Galaxy Version 1.3.0+galaxy0)*
   2. Parameters: Default; Input Transcriptome of Burkholderia gshA2 given to us by Dr. Van Laar
   3. Notes: 

      1. Falco acts as a more efficient software version of FastQC to check the quality of the raw reads of the transcriptome data
      2. Raw datasets of fwd and rev reads

         1. SA52159,wildtype,1
         2. SA52160,wildtype,2
         3. SA52161,wildtype,3
         4. SA52168,gshA2mutant,1
         5. SA52169,gshA2mutant,2
         6. SA52170,gshA2mutant,3
      3. QC notes:

         1. 
   4. Output: Set of 6 .txt files and 6 .html files (3 pairs of WT and 3 pairs of mutant type); Pick any of the .html samples, just make sure to pick the same file when doing FastP
   5. Files saved: Fwd and rev files of SA52159 WT1 (FWD\_Falco\_sr4 and REV\_Falco\_sr4)
2. Trim the raw WT reads to get rid of low quality ends

   1. Tool: FastP *(Galaxy Version 1.3.3+galaxy0)*
   2. Parameters: 

      1. Select for the "paired end reads" option
      2. Transcriptome file from Dr. Van Laar should auto. input itself into the data collection
   3. Notes:
   4. Output: FastP .html file of WT1 sample 

