### **Day 21 Workflow (4/30)**



1. Create a volcano plot to visualize differential gene expression data

   1. Tool: Volcano plot (Galaxy Version 4.0.2+galaxy0)
   2. Parameters: 

      1. Specify an input file - Differential Gene Expression of Broth and Plate file
      2. FDR (adj.'d p-val.) - Column 7
      3. Raw p-val. - Column 6
      4. Log Fold Change - Column 3
      5. Labels - Column 1
   3. Notes:

      1. Higher = lower p-value
      2. More right = more upregulated
      3. More left = more downregulated
   4. Result: Volcano plot graph **(SAVE)**
2. Transfer Differential Gene Expression tabular file into Excel

   1. Tool: Excel
   2. Parameters:

      1. Transfer Differential Gene Expression file into Transcriptome folder (module4)
      2. Open Excel

         1. "Open" (Top left of screen)
         2. "This PC"
         3. Select Differential Gene Expression of Broth and Plate file
         4. Go through default parameters
         5. Should have your new Excel file!
   3. Result: Excel file of gene expression data
3. Find top 10 up and down regulated genes

   1. Tool: Excel
   2. Parameters: 

      1. Select all data -> "Data" -> "Sort" -> Log2(FC)
      2. Highlight the top 10 and the bottom 10 genes
      3. Delete everything in between
      4. Save as either a tabular or a .csv
      5. Upload Excel file into Galaxy
   3. Results: Top up and down gene file **(SAVE)**, Upload to Galaxy
4. Join the normalized count and the top up and down regulated gene files

   1. Tool: Join two Datasets side by side on a specified field (Galaxy Version 2.1.3)
   2. Parameters: 

      1. Edit .csv file attribute to change it into a TABULAR file
      2. Join Top\&Bottom10genes file with the Normalized counts file
      3. Line up with Column 1 on each
      4. Keep the header lines - yes
   3. Results: Tabular table with 14 columns 
5. Cut out unnecessary columns

   1. Tool: Cut columns from a table (Galaxy Version 1.0.2)
   2. Parameters: 

      1. Input Join two Datasets file (Normalized counts + Top\&Bottom10gene file)
      2. Cut columns 8 - 14 **(WE KEEP THESE!)**
   3. Results: Cut file with gene names and the broth and plate replicants (7 total columns)
6. Make heat map

   1. Tool: heatmap2 (Galaxy Version 3.3.0+galaxy0)
   2. Parameters: 

      1. Input Cut file
      2. Data transformation - Log2(value+1) transform my data
      3. Choose type of color map to use and the name of the color pallete
   3. Interpretations: 

      1. Darker colors: higher levels of expression
      2. Lighter colors: lower levels of expression
   4. Results: PDF of heat map
7. Add column to denote what a gene is doing

   1. Tool: filter data on column using simple expressions (Galaxy Version 1.1.1)
   2. Parameters:

      1. Input promicromonospora.gff file
      2. With the following condition:  c3=='CDS'
   3. Notes:

      1. This step removes anything that is NOT an annotated as a coding DNA sequence (CDS)
   4. Results: Tabular file with all CDS genes included in Column 3
8. Focus on gene attributes

   1. Tool: Cut columns from a table (Galaxy Version 1.0.2)
   2. Parameters: 

      1. Input new Filter file (filtered out everything other than CDSs in Column 3)
      2. Cut columns c9
   3. Result: Tabular file with 1 giant column listing gene, gene details
9. Separate information into multiple columns from 1 giant column

   1. Tool: Convert delimiters to TAB (Galaxy Version 1.0.1)
   2. Parameters: 

      1. Input new Cut file (Tabular file w/ 1 giant column)
      2. Convert all - Semicolons
   3. Result: Tabular file with all genomic data separated into 17 columns
10. Get rid of Pattern=, we only want the gene in Column 2

    1. Tool: Replace Text in a specific column (Galaxy Version 9.5+galaxy3)
    2. Parameters: 

       1. Input Convert file
       2. Pattern - Pattern=
    3. Result: Tabular file with the Pattern= cut out of Column 2 
11. Get rid of everything but the gene name and the products

    1. Tool: Cut column from a table (Galaxy Version 1.0.2)
    2. Parameters: 

       1. Input Replace file
       2. Cut columns - c2,c8
    3. Result: Tabular file with the gene name and the product (2 columns total)
12. Join top and bottom 10 with gene name/product

    1. Tool: Join two Datasets side by side on a specified field (Galaxy Version 2.1.3)
    2. Parameters: 

       1. Join Gene name and gene product Cut file with the Top\&Bottom10 gene file
       2. Line up column 1 for both 
       3. Keep header titles - yes

