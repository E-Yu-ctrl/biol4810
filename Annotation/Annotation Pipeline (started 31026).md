Annotation Pipeline (started Tuesday 3/10/26)



Step 1: Filtering contigs shorter than 500 bp; tool used is "Filter FASTA - Galaxy Ver. 2.3"

Parameters: filtered on seq. length min. 500bp



Step 2: Quality assessment using checkM2 - Galaxy Version 1.1.0+galaxy0

Parameters: Model options -> "output quality prediction for both models for ea. genome"



Step 3: Genome annotation - Prokka (Galaxy Version 1.14.6+galaxy1)

Parameters: Force GenBank compliance - "Yes"



Step 4: Spp ID

Tool: NCBI BLAST - BLASTn (web)

Parameters" rRNA/ITS database



Step 5: Build phylogenetic tree

Tool: Type Strain Genome Server (TSGS) - tygs.dsmz.de (web)

Parameters: Whole-Proteome tree



Step 6" Visualize phylogenetic tree

Tool: interactive Tree of Life (iTOL) - iTOL v7 (web)

Parameters: Display bootstraps as text, rotated children, bold "Unk1\_SPAdes contigs"



Step 7: Avg. Nucleotide ID (ANI)

Tool: EZ BioCloud

Version: Website

Parameters: From NCBI genome database, downloaded the FASTA file for Salmonella Typhimurium (closest hit on NCBI 16S BLAST) and Salmonella bongori (more distant relative). Compared filtered\_contigs.fasta to the FASTA files from Typhimurium and S. bongori



1. cd into directory
2. git status
3. git add <name>
4. git status
5. got commit -m "message (uploading annotation folder from Bioinformatics and later added Step 7 to my notes"
