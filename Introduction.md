# Hi-M protocol

*Hi-M: Direct and simultaneous observation of transcription and chromosome architecture in single-cells*



[TOC]

## Introduction

Genomes are folded in a hierarchical organization that reflects and contribute to regulating transcription and other processes [(Bonev and Cavalli 2016)](https://paperpile.com/c/gKp8rW/NhOk8). However, our current understanding of chromatin architecture and how it is related to transcriptional regulation remains limited. In the last decade, two strategies became mainstream to study chromatin folding: chromosome conformation capture (3C and derivatives) and microscopy-based methods. 3C-like methods are powerful as they provide genome-wide information with kilobase (kb) resolution, but have several limitations: (1) most often they rely on population averaging, (2) they retrieve relative frequencies of pairwise interactions, (3) they have relatively low detection efficiency in single cells (<10% of the total contacts), (4) they are unable to provide spatial information (within the cell or the organism/ tissue), and (5) they do not permit simultaneous measurement of transcription and chromosome structure[(Giorgetti and Heard 2016)](https://paperpile.com/c/gKp8rW/ticDZ). Microscopy-based strategies on the other hand, employ fluorescence *in situ* hybridization (FISH) to target specific loci and can access their 3D position inside the nucleus, but until very recently were limited to the detection of a small number of genomic locations (typically 3-4). We and others have recently overcame several of these limitations to reconstruct chromatin architecture and detect transcriptional status at the same time in single-cells while retaining spatial information. This new technology, that we termed Hi-M (high-throughput, high-resolution, high-coverage microscopy-based technology, see below), addresses these shortcomings by employing high-throughput synthesis of short oligonucleotide (oligo) probes combined with RNA labeling and multiple rounds of hybridization in a sequential imaging scheme enabling the measurement of transcriptional state and the localization of tens of different genomic loci within intact *Drosophila* embryos [(Cardozo Gizzi et al. 2019)](https://paperpile.com/c/gKp8rW/jdOpb). Similar approaches have also been employed in concurrent work [(Bintu et al. 2018; Nir et al. 2018; Mateo et al. 2019)](https://paperpile.com/c/gKp8rW/vowXj+PJlsz+olAXp)**.**

### Principle of the method
Hi-M builds on recent innovations in FISH probe design based on high-throughput microarray oligos synthesis, namely Oligopaints (Beliveau et al. 2012, 2015) and on the pioneering design of multiplexing schemes for detecting hundreds of  RNA species by imaging (Lubeck et al. 2014; K. H. Chen et al. 2015). A microarray library with thousands of oligonucleotides (oligopool) is bioinformatically designed and commercially synthesized to target tens of different genomic locations. Each genomic locus (typically spanning 2-10 kb) is targeted by a unique set of 20-70 tiled oligos. We will refer to the genomic regions covered by these unique set of oligos as ‘barcodes’. Each oligo in a barcode contains three parts, a region of genomic homology, a barcode-specific readout sequence; and a priming region for PCR amplification (see Experimental design section). Labeling involves four steps. First, the oligopool library is enzymatically amplified and purified. Second, embryos are  collected and fixed. Third, embryos are labeled by an RNA hybridization and signal amplification step. Fourth, the oligopool is hybridized to genomic DNA. After labeling, samples are mounted onto a microfluidic chamber connected to a microfluidics pump system and mounted into an automated widefield fluorescence microscope. In an initial round, DAPI and RNA signals are acquired in multiple regions of interest (ROIs). Then, the imaging of each barcode requires: (1) labeling of the sample with barcode-specific, fluorescently-labeled readout oligonucleotides (readout probes); (2) removal of unbound readout oligos by washing; (3) acquisition of 3D, two-color images for all ROIs and (4) photobleaching. This process is repeated sequentially for each barcode. In all sequential rounds, a second, spectrally different, fluorescent oligo is present and used as the fiducial barcode for drift correction. Next, images are processed to: segment DNA masks, determine the transcriptional status of each cell, retrieve the 3D position of each barcode in every ROI with sub-pixel accuracy, and correct drift during acquisition and between cycles of hybridization. Finally, the 3D coordinates of each barcode detected in each cell are used to reconstruct Hi-M matrices containing mean pairwise distances and absolute contact probabilities. 


### Applications of the method
We have developed Hi-M to explore genome architecture and transcription in intact Drosophila embryos. However, Hi-M can be used in a large variety of model systems. For instance, adaptation to cultured cells should be straightforward. Cultured cells can be readily attached to the coverslip by standard procedures (e.g. by growing them in treated coverslips conductive of cell adhesion). In fact, cultured cells exhibit lower auto-fluorescence than organisms, thus the application of Hi-M should result in an increased barcode detection and localization precision. Hi-M could also be adapted to thick tissues and organoids by relying on cryo-sectioning (Jeffrey R. Moffitt et al. 2018) or on optical-sectioning. 
	
The RNA/DNA staining procedures described in this protocol are fully compatible with other imaging modalities, such as 3D Structured Imaging Microscopy (3D-SIM) or Stochastic optical reconstruction microscopy (STORM) (Bintu et al. 2018; Nir et al. 2018). The acquisition of super-resolution images is typically slower than for wide-field microscopy images, therefore limiting the throughput of a Hi-M acquisition. Thus, a compromise between resolution and throughput will have to be found depending on the problem under study. In addition, most super-resolution microscopies are not well adapted to thick specimens, thus their use in Hi-M will be mainly limited to thin samples. 
	
The flexibility afforded by Oligopaints in the design of probes would enable the adaptation of Hi-M to explore chromosome conformation at different length scales (e.g. chromosomal(Rosin, Nguyen, and Joyce 2018), compartment(Nir et al. 2018) or TAD levels(Cardozo Gizzi et al. 2019; Mateo et al. 2019)). In the present protocol, barcodes contain ~20-90 primary oligos and cover 2-10 kb to produce diffraction-limited spots and ensure excellent signal-to-noise ratios (SNR, defined as the maximum intensity of a spot divided by the standard deviation of the background). Labeling of smaller genomic regions is possible but at the expense of reduced SNR levels (i.e. reduced localization precision). 

### Limitations

A current limitation of Hi-M is the time required for the acquisition of an entire dataset: typically 2-3 days to image 50-70 barcodes in 30 fields of view (representing ~50000 cells for Drosophila embryos). Thus, typically a balance between experimental time and the number of barcodes imaged needs to be found. For instance, 70 barcodes could be used to image an extended genomic region (e.g. 3.5 Mb) at low resolution (50 kb between barcodes), or to image a single genomic locus (e.g. 150kb) at high resolution (~2kb).

A second limitation is the minimal number of primary probes per barcode. The values provided in this protocol (see Experimental Design section) ensure robust detection with high localization precision. A reduction in the number of primary probes could lead to decreased levels of detection and degraded localization precision. A possible future solution to this limitation may be to increase the number of imaging probes by encoding more readout probes per barcode (e.g. using SABER-FISH(Kishi et al. 2018)), but ultimately this approach may limit the specificity of labeling. 

A third limitation is the reduced efficiency of barcode detection, currently close to 60-70%. Thus, a barcode is observed in only ~6-7 out of 10 nuclei. This entails a reduced number of cells containing all barcodes. 
	 	
A fourth limitation arises from the high cost of fluorescently-labeled oligos (~500$ each). As each barcode is detected by a specific fluorescently-labeled readout probe, the price of an experiment increases linearly with the number of barcodes. A new strategy that can considerably reduce the experimental cost has been recently described in two publications(Mateo et al. 2019; Fields et al. 2019). Instead of using a fluorescently labeled oligo for each barcode, a combination of two oligos is used: a non-fluorescent oligo specific for each barcode (bridge oligo) and a single fluorescent oligo common to all barcodes (imaging oligo). The bridge oligo contains 20 nucleotides (-nt) complementary to the barcode sequence, followed by a 10-nt “toehold” spacer sequence and a 20-nt sequence complementary to the imaging oligo(Lidke et al. 2017). With this design, the same fluorescently-labeled imaging oligo can be used to read all barcodes, with barcode specificity provided by the bridge oligo. Furthermore, this strategy can also be exploited to remove the fluorescence after each imaging cycle by the use of displacement oligos. Displacement oligos are complementary to the “toehold” and bridge probe sequences, therefore they displace the bridge probe from the barcode and in doing so they also remove the imaging probe. 	
	
A final limitation relies on the ability of Hi-M to detect several RNA species at once. The Hi-M protocol described here enables the simultaneous detection of chromosome conformation together with a single RNA species. In future, additional  RNA species could be labeled by using a sequential TSA reaction with alternative conjugation molecules (e.g. biotin) or by relying on oligonucleotide-derivatized antibodies. It is worth noting that TSA amplification is non-linear, therefore quantification of RNA levels requires proper calibration.

### Comparison with other methods

Compared to traditional FISH, Hi-M has two main advantages: (1) it uses oligo probes, that provide design flexibility and higher efficiency of labeling compared to double stranded BAC or amplicon-based probes(Roohi et al. 2008; Bienko et al. 2013), and (2) it employs a multiplexed approach that does not rely on the use of spectrally different fluorophores (limited to 2-4 in most applications). The overall strategy of Hi-M is conceptually  similar to recent work employing sequential imaging schemes and oligopaint labeling (Wang et al. 2016; Bintu et al. 2018; Nir et al. 2018; Mateo et al. 2019). The main differences with these studies are: (1) Hi-M enables simultaneous detection of RNA status and chromosome organization without sample unmounting and probe re-hybridization. Other approaches also enable RNA/DNA detection, but require the hybridization and imaging of RNA probes, unmounting of the sample followed by degradation of RNA, hybridization of DNA probes, and then remounting and imaging of the same cryo-sectioned samples(Mateo et al. 2019); (2) Hi-M allows, in contrast with other studies (Mateo et al. 2019; Bintu et al. 2018; Nir et al. 2018), for the imaging of entire, intact organisms.
	
Multiplexing has also been recently achieved in the single-cell imaging of multiple RNA species (Shah et al. 2018; K. H. Chen et al. 2015; Jeffrey R. Moffitt et al. 2018; Eng et al. 2017). These studies used combinatorial schemes to target ~140(K. H. Chen et al. 2015; Jeffrey R. Moffitt et al. 2018) to ~10,000 genes(Shah et al. 2018; Eng et al. 2017) using only ~20 hybridization cycles. RNA is typically present in many copies per cell and these copies are spatially well separated, making it possible to decode species using combinatorial approaches. Currently, the use of combinatorial approaches to label DNA are limited by the spatial overlap of barcodes, the small number of DNA molecules detected (typically 1-4 depending on ploidy), and by the reduced efficiency of detection (~60%, see above). Excitingly, combinatorial approaches based on other principles(Fields et al. 2019) may be usable in the near future to considerably increase the number of detected barcodes without a linear increase in the number of hybridization cycles.   
	
Hi-M and similar approaches based on FISH are carried out in fixed samples, thus they cannot provide dynamic information. Live imaging of single genomic loci has been achieved using a catalytically inactive Cas nuclease that is targeted to a loci by a small guide RNA (sgRNA) (for a review see(Wu et al. 2019)). Typically CRISPR-based imaging records the position of two genomic loci, although targeting up to 6 genomic loci has been achieved for repetitive sequences(Ma et al. 2016). Imaging non-repetitive sequences has been proven challenging due to the complexity of simultaneously co-expressing multiple sgRNA species in one cell. Furthermore, off-target binding and background fluorescence can further limit the application of current CRISPR-based imaging methods. More recently, a radically different approach successfully followed the 3D position of a single gene in real time while simultaneously monitoring mRNA synthesis in the same cell(Germier et al. 2017; H. Chen et al. 2018) by combining stem-loop-based labeling  (MS2 and/or PP7(Yunger et al. 2010; Larson et al. 2011; Fukaya, Lim, and Levine 2016)) and the ParS/ParB system(Saad et al. 2014). This approach was used to study the position of a genomic locus and a transcription spot at the same time in living Drosophila embryos(H. Chen et al. 2018). This approach requires genetic manipulation to introduce ectopic sequences, and is limited at present to a maximum of two colors (typically a transcript and a genomic locus).



## References

Bantignies, Frédéric, and Giacomo Cavalli. 2014. “Topological Organization of Drosophila Hox Genes Using DNA Fluorescent in Situ Hybridization.” Methods in Molecular Biology  1196: 103–20.

Beliveau, Brian J., Alistair N. Boettiger, Maier S. Avendaño, Ralf Jungmann, Ruth B. McCole, Eric F. Joyce, 

Caroline Kim-Kiselak, et al. 2015. “Single-Molecule Super-Resolution Imaging of Chromosomes and in Situ Haplotype Visualization Using Oligopaint FISH Probes.” Nature Communications. https://doi.org/10.1038/ncomms8147.

Beliveau, Brian J., Eric F. Joyce, Nicholas Apostolopoulos, Feyza Yilmaz, Chamith Y. Fonseka, Ruth B. McCole, Yiming Chang, et al. 2012. “Versatile Design and Synthesis Platform for Visualizing Genomes with Oligopaint FISH Probes.” Proceedings of the National Academy of Sciences of the United States of America 109 (52): 21301–6.

Beliveau, Brian J., Jocelyn Y. Kishi, Guy Nir, Hiroshi M. Sasaki, Sinem K. Saka, Son C. Nguyen, Chao-Ting Wu, and Peng Yin. 2018. “OligoMiner Provides a Rapid, Flexible Environment for the Design of Genome-Scale Oligonucleotide in Situ Hybridization Probes.” Proceedings of the National Academy of Sciences of the United States of America 115 (10): E2183–92.

Bienko, Magda, Nicola Crosetto, Leonid Teytelman, Sandy Klemm, Shalev Itzkovitz, and Alexander van Oudenaarden. 2013. “A Versatile Genome-Scale PCR-Based Pipeline for High-Definition DNA FISH.” Nature Methods. https://doi.org/10.1038/nmeth.2306.

Bintu, Bogdan, Leslie J. Mateo, Jun-Han Su, Nicholas A. Sinnott-Armstrong, Mirae Parker, Seon Kinrot, Kei 

Yamaya, Alistair N. Boettiger, and Xiaowei Zhuang. 2018. “Super-Resolution Chromatin Tracing Reveals Domains and Cooperative Interactions in Single Cells.” Science 362 (6413). https://doi.org/10.1126/science.aau1783.

Boettiger, Alistair Nicol, and Michael Levine. 2013. “Rapid Transcription Fosters Coordinate Snail Expression in the Drosophila Embryo.” Cell Reports 3 (1): 8–15.

Bonev, Boyan, and Giacomo Cavalli. 2016. “Organization and Function of the 3D Genome.” Nature Reviews. Genetics 17 (12): 772.

Boyle, Shelagh, Matthew J. Rodesch, Heather A. Halvensleben, Jeffrey A. Jeddeloh, and Wendy A. Bickmore. 2011. “Fluorescence in Situ Hybridization with High-Complexity Repeat-Free Oligonucleotide Probes Generated by Massively Parallel Synthesis.” Chromosome Research: An International Journal on the Molecular, Supramolecular and Evolutionary Aspects of Chromosome Biology 19 (7): 901–9.

Cardozo Gizzi, Andrés M., Diego I. Cattoni, Jean-Bernard Fiche, Sergio M. Espinola, Julian Gurgo, Olivier Messina, Christophe Houbron, et al. 2019. “Microscopy-Based Chromosome Conformation Capture Enables Simultaneous Visualization of Genome Organization and Transcription in Intact Organisms.” Molecular Cell 74 (1): 212–22.e5.

Cattoni, Diego I., Andrés M. Cardozo Gizzi, Mariya Georgieva, Marco Di Stefano, Alessandro Valeri, Delphine Chamousset, Christophe Houbron, et al. 2017. “Single-Cell Absolute Contact Probability Detection Reveals Chromosomes Are Organized by Multiple Low-Frequency yet Specific Interactions.” Nature Communications 8 (1): 1753.

Chen, Hongtao, Michal Levo, Lev Barinov, Miki Fujioka, James B. Jaynes, and Thomas Gregor. 2018. “Dynamic Interplay between Enhancer–promoter Topology and Gene Activity.” Nature Genetics. https://doi.org/10.1038/s41588-018-0175-z.

Chen, Kok Hao, Alistair N. Boettiger, Jeffrey R. Moffitt, Siyuan Wang, and Xiaowei Zhuang. 2015. “RNA Imaging. Spatially Resolved, Highly Multiplexed RNA Profiling in Single Cells.” Science 348 (6233): aaa6090.

Eng, Chee-Huat Linus, Sheel Shah, Julian Thomassie, and Long Cai. 2017. “Profiling the Transcriptome with RNA SPOTs.” Nature Methods. https://doi.org/10.1038/nmeth.4500.

Fields, Brandon D., Son C. Nguyen, Guy Nir, and Scott Kennedy. 2019. “A Multiplexed DNA FISH Strategy for Assessing Genome Architecture in Caenorhabditis Elegans.” eLife 8 (May). https://doi.org/10.7554/eLife.42823.

Fukaya, Takashi, Bomyi Lim, and Michael Levine. 2016. “Enhancer Control of Transcriptional Bursting.” Cell 166 (2): 358–68.

Fung, J. C., W. F. Marshall, A. Dernburg, D. A. Agard, and J. W. Sedat. 1998. “Homologous Chromosome Pairing in Drosophila Melanogaster Proceeds through Multiple Independent Initiations.” The Journal of Cell Biology 141 (1): 5–20.

Gelali, Eleni, Gabriele Girelli, Masahiro Matsumoto, Erik Wernersson, Joaquin Custodio, Ana Mota, Maud 

Schweitzer, et al. 2019. “iFISH Is a Publically Available Resource Enabling Versatile DNA FISH to Study Genome Architecture.” Nature Communications. https://doi.org/10.1038/s41467-019-09616-w.

Germier, Thomas, Silvia Kocanova, Nike Walther, Aurélien Bancaud, Haitham Ahmed Shaban, Hafida Sellou, Antonio Zaccaria Politi, Jan Ellenberg, Franck Gallardo, and Kerstin Bystricky. 2017. “Real-Time Imaging of a Single Gene Reveals Transcription-Initiated Local Confinement.” Biophysical Journal 113 (7): 1383–94.

Giorgetti, Luca, and Edith Heard. 2016. “Closing the Loop: 3C versus DNA FISH.” Genome Biology 17 (1): 215.
Kishi, J. Y., B. J. Beliveau, S. W. Lapan, E. R. West, and A. Zhu. 2018. “SABER Enables Highly Multiplexed and Amplified Detection of DNA and RNA in Cells and Tissues.” bioRxiv. https://www.biorxiv.org/content/10.1101/401810v1.abstract.

Larson, Daniel R., Daniel Zenklusen, Bin Wu, Jeffrey A. Chao, and Robert H. Singer. 2011. “Real-Time Observation of Transcription Initiation and Elongation on an Endogenous Yeast Gene.” Science 332 (6028): 475–78.

Lidke, Diane S., Cheyenne Martin, Farzin Farzam, Jeremy S. Edwards, Sandeep Pallikkuth, Mathew R. Lakin, and Keith A. Lidke. 2017. “Sequential Super-Resolution Imaging Using DNA Strand Displacement.” bioRxiv. https://doi.org/10.1101/237560.

Lubeck, Eric, Ahmet F. Coskun, Timur Zhiyentayev, Mubhij Ahmad, and Long Cai. 2014. “Single-Cell in Situ RNA Profiling by Sequential Hybridization.” Nature Methods.

Ma, Hanhui, Li-Chun Tu, Ardalan Naseri, Maximiliaan Huisman, Shaojie Zhang, David Grunwald, and Thoru Pederson. 2016. “Multiplexed Labeling of Genomic Loci with dCas9 and Engineered sgRNAs Using CRISPRainbow.” Nature Biotechnology 34 (5): 528–30.

Mateo, Leslie J., Sedona E. Murphy, Antonina Hafner, Isaac S. Cinquini, Carly A. Walker, and Alistair N. Boettiger. 2019. “Visualizing DNA Folding and RNA in Embryos at Single-Cell Resolution.” Nature 568 (7750): 49–54.

Moffitt, Jeffrey R., Dhananjay Bambah-Mukku, Stephen W. Eichhorn, Eric Vaughn, Karthik Shekhar, Julio D. 

Perez, Nimrod D. Rubinstein, et al. 2018. “Molecular, Spatial, and Functional Single-Cell Profiling of the Hypothalamic Preoptic Region.” Science 362 (6416). https://doi.org/10.1126/science.aau5324.

Moffitt, Jeffrey R., Junjie Hao, Guiping Wang, Kok Hao Chen, Hazen P. Babcock, and Xiaowei Zhuang. 2016. “High-Throughput Single-Cell Gene-Expression Profiling with Multiplexed Error-Robust Fluorescence in Situ Hybridization.” Proceedings of the National Academy of Sciences. https://doi.org/10.1073/pnas.1612826113.

Moffitt, J. R., and X. Zhuang. 2016. “RNA Imaging with Multiplexed Error-Robust Fluorescence In Situ Hybridization (MERFISH).” Methods in Enzymology 572 (April): 1–49.

Nir, Guy, Irene Farabella, Cynthia Pérez Estrada, Carl G. Ebeling, Brian J. Beliveau, Hiroshi M. Sasaki, S. Dean 

Lee, et al. 2018. “Walking along Chromosomes with Super-Resolution Imaging, Contact Maps, and Integrative Modeling.” PLoS Genetics 14 (12): e1007872.

Raj, Arjun, Patrick van den Bogaard, Scott A. Rifkin, Alexander van Oudenaarden, and Sanjay Tyagi. 2008. “Imaging Individual mRNA Molecules Using Multiple Singly Labeled Probes.” Nature Methods 5 (10): 877–79.

Roohi, J., M. Cammer, C. Montagna, and E. Hatchwell. 2008. “An Improved Method for Generating BAC DNA Suitable for FISH.” Cytogenetic and Genome Research 121 (1): 7–9.

Rosin, Leah F., Son C. Nguyen, and Eric F. Joyce. 2018. “Condensin II Drives Large-Scale Folding and Spatial Partitioning of Interphase Chromosomes in Drosophila Nuclei.” PLoS Genetics 14 (7): e1007393.

Rouillard, Jean-Marie, Michael Zuker, and Erdogan Gulari. 2003. “OligoArray 2.0: Design of Oligonucleotide Probes for DNA Microarrays Using a Thermodynamic Approach.” Nucleic Acids Research 31 (12): 3057–62.

Saad, Hicham, Franck Gallardo, Mathieu Dalvai, Nicolas Tanguy-le-Gac, David Lane, and Kerstin Bystricky. 2014. “DNA Dynamics during Early Double-Strand Break Processing Revealed by Non-Intrusive Imaging of Living Cells.” PLoS Genetics 10 (3): e1004187.

Shah, Sheel, Yodai Takei, Wen Zhou, Eric Lubeck, Jina Yun, Chee-Huat Linus Eng, Noushin Koulena, et al. 2018. “Dynamics and Spatial Genomics of the Nascent Transcriptome by Intron seqFISH.” Cell 174 (2): 363–76.e16.

Shpiz, Sergey, Sergey Lavrov, and Alla Kalmykova. 2014. “Combined RNA/DNA Fluorescence in Situ Hybridization on Whole-Mount Drosophila Ovaries.” Methods in Molecular Biology  1093: 161–69.

Trcek, Tatjana, Timothée Lionnet, Hari Shroff, and Ruth Lehmann. 2017. “mRNA Quantification Using Single-Molecule FISH in Drosophila Embryos.” Nature Protocols 12 (7): 1326–48.

Wang, Siyuan, Jun-Han Su, Brian J. Beliveau, Bogdan Bintu, Jeffrey R. Moffitt, Chao-Ting Wu, and Xiaowei 

Zhuang. 2016. “Spatial Organization of Chromatin Domains and Compartments in Single Chromosomes.” Science. https://doi.org/10.1126/science.aaf8084.

Wu, Xiaotian, Shiqi Mao, Yachen Ying, Christopher J. Krueger, and Antony K. Chen. 2019. “Progress and Challenges for Live-Cell Imaging of Genomic Loci Using CRISPR-Based Platforms.” Genomics, Proteomics & Bioinformatics, January. https://doi.org/10.1016/j.gpb.2018.10.001.

Yunger, Sharon, Liat Rosenfeld, Yuval Garini, and Yaron Shav-Tal. 2010. “Single-Allele Analysis of Transcription Kinetics in Living Mammalian Cells.” Nature Methods 7 (8): 631.