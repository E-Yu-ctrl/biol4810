Day 19 Workflow - Transcriptome (4/23)



1. Check quality of reads

   1. Tool: Falco (Galaxy Version 1.2.4+galaxy0)
   2. Parameters: Default; Input Transcriptome dataset given to us from Van Laar
   3. File saved: FWD and REV reads of a Plate sample (Plate3\_S191\_001 -> FWD-Plate3-Reads.html and REV\_Plate3\_Reads.html)

      1. Notes:

         1. Nothing was flagged as being a poor quality read
         2. Phread quality for both the FWD and REV were consistently at 40
         3. Both FWD and REV failed at sequence quality per tile
         4. Both passed the per sequence quality score
         5. Noticeable difference b/n FWD and REV per base sequence content, both fail
         6. FWD reads failed the per sequence GC content, REV received a warning
         7. Noticeable difference in the per base nitrogen content
         8. Warning for sequence length distribution, lots of sequences in the 146-149bp range
         9. Both fail the sequence duplication levels, graphs look similar though
         10. Both fail in the overrep.'d sequences, no hits for anything in both
         11. Both pass adapter content

             1. REV has a higher % of sequences with adapter before position (0.3 - 0.5%, or 30 - 50%)
             2. FWD ranged from 0 - 0.2%, or 0 - 20%)
2. Trim reads

   1. FastP (Galaxy Version 1.3.1+galaxy0)
   2. Parameters: Select for the paired reads option and then the Transcriptome dataset from VL should pop into the dropdown menu -> Run tool
   3. File saved: FastP of Plate3 file (FASTP\_Plate3.html)

      1. Notes:

         1. Mean reads before and after filtering remained that same at 133bp
3. Align raw reads to a provided sample genome

   1. Tool: HISAT2 (Galaxy Version 2.2.2+galaxy0)
   2. Parameters: Source for the reference genome -> Use a genome from history, ref, genome should default to the promicromonospora.fasta file; Single or paired library -> Paired-end Dataset Collection, Paired Collection should default to your FastP Paired-End output file -> Run Tool
   3. File saved: N/A
4. Take short reads and figure out where they belong and how they fit together

   1. Tool: StringTie (Galaxy Version 2.2.3+galaxy0)
   2. Parameters: Input options -> Short reads, HISAT2 output collection should auto. go into dropdown menu -> Run Tool
   3. File saved: N/A
5. Merge transcripts together 

   1. Tool: StringTie merge (Galaxy Version 2.2.3+galaxy0)
   2. Parameters: "Transcripts" -> "Data Collection" -> select StringTie output file -> Run Tool
   3. File saved: 
6. Compare transcripts to 

   1. Tool: GffCompare
7. asdf

   1. Tool: featureCounts

