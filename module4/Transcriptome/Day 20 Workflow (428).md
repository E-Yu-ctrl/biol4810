## **Day 20 Workflow (4/28)**



1. Find differential gene expression

   1. DESeq2 (Galaxy Version 2.11.40.8+galaxy2)
   2. Parameters: 

      1. Factor - Growth\_Media

         1. Factor level - Broth

            1. Input 3 count tables of broth counts
         2. Factor level - Plate

            1. Input 3 count tables of plate counts
      2. Advanced options

         1. Yes to use beta priors
      3. Output options

         1. Generate plots for visualizing the analysis results
         2. Output normalized counts
   3. Results: Result and plot files, download plots, make sure to visualize them 

      1. Focus on adjusted p-value (P-ad column)
2. Filter out adjusted p-values over 0.05

   1. Tool: Filter data on any column using simple expressions (Galaxy Version 1.1.1)
   2. Parameters: 

      1. Input DESeq2 collection
      2. With following conditions: c7<0.05
   3. Leave everything else as default
   4. Results: 
3. Filter out insignificant data from log2(FC)

   1. Tool: Filter data on any column using simple expressions (Galaxy Version 1.1.1)
   2. Parameters: 

      1. Input previous Filter collection
      2. With following conditions:

         1. abs(c3)>1
   3. Plot interpretations:

      1. See how different growth medias (broth vs plate) are similar and different when it come to the data they have
      2. Broth clustered with broth, plate clustered with plate
      3. See extend of gene upregulation and downregulation
4. Create headers to add onto filtered dataset

   1. Tool: Plain text editor (Notebook)
   2. Parameters: Type the following in a single line, press tab after every header to separate them (don't mind the space or if the headers wrap into the next line)

      1. Gene ID, base mean, log2(FC), StdErr, Wald-Stats, P-value, P-adj
      2. Copy everything in the text editor
      3. Go back to Galaxy and go to Upload
      4. Paste/Fetch data
      5. Type in "Header" and change the file type to "Tabular"
      6. Paste all the header titles into the box below
      7. Start
   3. Results: Header file in Galaxy
5. Put header on file

   1. Tool: Concatenate multiple datasets or collections (Galaxy Version 1.0.0)
   2. Parameters: 

      1. Concatenate dataset - Header file
      2. Dataset - Most recent Filter file
   3. Results: Differential Gene Expression of Broth and Plate file (DL it!)
6. Upload everything to GitHub

   1. Tool: GitBash
   2. Parameters: 

      1. Hold Shift and right click into Unix\_BIOL4810
      2. Drag new folder into GitBash (module4)
      3. git add module 4/\*
      4. git status (to check everything has been uploaded to GitHub)
      5. git commit -m "Adding new files from DESeq2 and updated Transcriptome notes"
      6. git push
      7. Check that everything has been uploaded by going into GitHub

