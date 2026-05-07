# **Section Report 2 (Due 3/24/26)**



Step 1: Download raw reads from "Sequences for BIOL 4810" from Dr. Tricia Van Laar and upload them to FastQC on Galaxy under *"Sequence Reads"*

Tool: FastQC (Galaxy)

Ver.: Galaxy Version 0.74+galaxy1

Parameter: "Multiple datasets", upload both raw read files (Emma\_R1.fastq, Emma\_R2.fastq), download HTML files

Files saved: HTML files of the raw reads (FastQC\_SR2\_Forward.HTML and FastQC\_SR2\_Reverse.HTML),  screenshot quality plot in reverse file



Step 2: Upload raw reads to fastp as a *paired collection* for genome trimming

Tool: fastp (Galaxy)

Ver.: (Galaxy Version 1.1.0+galaxy0

Parameters: Default

File saved: fastp file of raw reads (fastp\_SR2.HTML)



Step 3: Upload trimmed/fastp reads to FastQC

Tool: FastQC (Galaxy)

Ver.: Galaxy Version 0.74+galaxy1

Parameters: "Dataset collection" -> "25: fastp on collection 12: paired-end output"

Files saved: Trimmed FastQC files (FORWARDTrimmedFastQC\_SR2.HTML, REVERSETrimmedFastQC\_SR2.HTML), screenshot of trimmed reverse quality plot



Step 4: Upload trimmed FastQC file (fastp file) to SPAdes for genome assembly

Tool: SPAdes (Galaxy)

Ver.: Galaxy Version 4.2.0+galaxy0

Parameters: Default

File saved: contigs FASTA file (SR2\_unknowncontigs.fasta)



Step 5: Upload contigs FASTA file to Quast to see genome evaluation

Tool: Quast (Galaxy)

Ver.: Galaxy Version 5.3.0+galaxy1

Parameters: Individual assembly, use contigs FASTA file (not scaffolds file)

Files saved: Quast PDF file (QuastSR2.pdf)



Step 6: Check genome quality with CheckM2



6a) Tool: Filter FASTA (Galaxy)

Ver.: Galaxy Version 2.3

Parameters: Criteria for filtering on the sequences -> Sequence length -> Min. length -> 500; Default for everything else

File saved: Filtered contigs file (SR2FilteredContigs.fasta)



6b) Tool: CheckM2

Ver.: Galaxy Version 1.1.0+galaxy0

Parameters: Model options -> Output quality predictions for both models

File saved:



Step 7: Annotate genome w/ Prokka

Tool: Prokka (Galaxy)

Ver.: Galaxy Version 1.14.6+galaxy1

Parameters Force GenBank compliance -> Yes; Genus name: *Salmonella*

File saved: Prokka txt, gbk, and ffn files (SR2\_Prokka.txt, SR2\_Prokka.ffn.fasta, and SR2\_Prokka.gbk)



Step 8: Use NCBI BLAST for species ID of 16S seq.

Tool: NCBI BLASTn

Ver.: N/A

Parameters: Database -> 16S ribosomal RNA; everything else is default

Files saved: S. enterica serovar Typhimurium 16S rRNA fasta file (S.enterica.serovar.Typh.fasta) and the Enterobacter cloacae 16S rRNA fasta file (Enterobacter.cloacae.fasta)



Step 9: Compare genomes with ANI via EZCloudBio ANI

Tool: EZCloudBio ANI

Ver.: N/A

Parameters: Default; Upload filtered contigs file (SR2FilteredContigs.fasta)

Files saved: N/A



Step 10: Upload filtered contigs to TYGS to view it as a phylogenetic tree

Tool: TYGS (Type-Strain Genome Server)

Ver.: N/A

Parameters: Default; Upload filtered contigs file (SR2FilteredContigs.fasta)

File saved: N/A, TYGS and iTOL is not working has not been working since 3pm of Monday, March 23



Step 11: Find antimicrobial resistance (AMR) genes with CARD/RGI system, upload filtered contigs fasta file (SR2FilteredContigs.fasta)

Tool: CARD, RGI

Ver.: RGI 6.0.5, CARD 4.0.1

Parameters: Default

File saved: Screenshot of results (SR2\_CARD+RGIresults.jpeg)



Step 12: ResFinder for antimicrobial resistance (AMR) genes

Tool: ResFinder

Ver.: ResFinder 4.7.2, ResFinder-2.5.1 (database)

Parameters: Default; Upload filtered contigs file (SR2FilteredContigs.fasta)

File saved: Screenshot of results table with resistant genes (SR2\_ResFinder\_results.jpeg)



Step 13: PathogenFinder for risk of causing disease to humans

Tool: PathogenFinder

Ver.: 0.6.0

Parameters: Default; Upload filtered contigs file (SR2FilteredContigs.fasta)

File saved: Screenshot results page (SR2\_PathogenFinder\_results)



Step 14: Use ABRicate in Galaxy to find AMR genes and virulence factors

Tool: ABRicate (Galaxy)

Ver.: Galaxy Version 1.0.1

Parameters: Advanced options -> switch database to VFDB; Everything else is default; Upload filtered contigs file (SR2FilteredContigs.fasta)

File saved: ABRicate tubaular file (SR2\_abricate\_table)



Step 15: Secondary metabolite production

Tool: antiSMASH

Ver.: 8.0.4

Parameters: Default; Upload filtered contigs file (SR2FilteredContigs.fasta)

File saved: Screenshot of antiSMASH overview page (SR2-antismash-results)



Step 16: Search for pathogenicity islands

Tool: IslandViewer

Ver.: 4

Parameters: Genome upload -> upload Prokka GenBank file -> run; Everything else is default

File saved: Screenshot of IslandViewer map (SR2\_IVmap)



Step 17: Search for CRISPR regions

Tool: CRISPRCasFinder

Version: 1.1.2

Parameters: Default; Upload filtered contigs (SR2FilteredContigs.fasta)

File saved: Screenshot of results (arrays \& Cas summary)



Step 18: Upload everything to GitHub

