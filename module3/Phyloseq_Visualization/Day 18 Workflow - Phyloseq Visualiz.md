Day 18 Workflow - Phyloseq Visualization (4/21)



1. Find alpha diversity of phyloseq object in Galaxy

   1. Tool: Phyloseq alpha diversity via interactive tools (Galaxy Version 1.54.0+galaxy0)
   2. Parameters: "Under Aesthetic Mapping" -> Color - SampleSource, Shape - InfectionStatus, Alpha measures -> Shannon, Observed, Simpson -> Download PDf
   3. File saved: Alpha diversity plot (AlphaDiversity.pdf)
2. Beta diversity in phyloseq

   1. Tool: Ordination via phyloseq interactive tool
   2. Parameters: 

      1. Under "Structure"

         1. Method - NMDS
         2. Distance - bray
      2. Under Aesthetic Mapping

         1. Color - sample source
         2. Shape - infection status
      3. DL PDF
   3. File saved: Beta diversity plot (BetaDiversity.pdf)
3. Taxonomic bar plot

   1. Tool: Bar Chart
   2. Parameters: 

      1. Bar Chart 1:

         1. Fill - Phylum
         2. Facet by variable - SampleSource
         3. Keep 'Others' - True
         4. Keep 'Not Assigned' - True
         5. Normalize - True
      2. Bar chart 2:

         1. Fill variable - Phylum
         2. Facet by variable - InfectionStatus
         3. Keep 'Others' - True
         4. Keep 'Not Assigned' - True
         5. Normalize - True
      3. DL PDF
   3. Files saved: 2 bar charts (BarChart1-SampleSource.pdf and BarChart2-InfectionStatus.pdf)

