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
   4. Result: Volcano plot graph (SAVE)
2. Transfer Differential Gene Expression tabular file into Excel

   1. Tool: Excel
   2. Parameters:

      1. Transfer Differential Gene Expression file into Transcriptome folder (module4)
      2. Open Excel

         1. Open (Top left of screen)
         2. This PC
         3. Select Differential Gene Expression of Broth and Plate file
         4. Go through default parameters
         5. Should have your Excel file!
   3. Result: Excel file of gene expression data
3. Find top 10 up and down regulated genes

   1. Tool: Excel
   2. Parameters: 

      1. Select all data -> "Data" -> "Sort" -> Log2(FC)
      2. Highlight the top 10 and the bottom 10 genes
      3. Delete everything in between
      4. Save as either a tabular or a .csv
      5. Upload Excel file into Galaxy
   3. Results: Top up and down gene file (SAVE), Upload to Galaxy
4. Join the normalized counts and the top up and down regulated genes

   1. Tool: Join two datasets side by side on a specified field (Galaxy Version 2.1.3)
   2. Parameters: 

      1. Edit .csv file attribute to change it into a TABULAR file
      2. Join Top\&Bottom10genes file with the Normalized counts file
      3. Line up with Column 1 on each
      4. Keep the header lines - yes
   3. Results: Tabular table with 14 columns 
5. Cut out unnecessary columns

   1. Tool: Cut columns from a table (Galaxy Version 1.0.2)
   2. Parameters: 

      1. Input Join two Datasets file
      2. Cut out columns 8 - 14
   3. Results: Cut file with gene names and the broth and plate replicants (7 total columns)
6. Make heat map

   1. Tool: heatmap2 (Galaxy Version 3.3.0+galaxy0)
   2. Parameters: 

      1. Input Cut file
      2. Data transformation - Log2(value+1) transform my data
      3. Choose type of color map to use and the name of the color pallete
   3. Results: PDF of heat map

