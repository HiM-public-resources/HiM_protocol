# Hi-M protocol

*Hi-M: Direct and simultaneous observation of transcription and chromosome architecture in single-cells*



[TOC]

## Procedure


### Design of Oligopaint libraries * Timing 4-5 h 

1. Download Oligopaint scripts(Beliveau et al. 2012) and .bed files containing all primary oligos following the instructions in http://genetics.med.harvard.edu/oligopaints.
CRITICAL STEP: .bed files contain the sequences of oligos previously mined using OligoArray(Rouillard, Zuker, and Gulari 2003) or OligoMiner(Beliveau et al. 2018), covering the Drosophila non-repetitive genome. 
2. Define genomic locations of interest (barcodes) and use grabRegion.py to select the oligos corresponding to each barcode. Register the number of oligos in each barcode.
CRITICAL STEP: Include also a fiducial barcode.
3. An output text file is created with a list of oligos for each barcode. Concatenate all output files using a Linux command line. 
4. Create a unique text file with the readout sequences for all barcodes. It consists of a line for each barcode. In each line, add i) the 5’ readout sequence, ii) the 3’ readout sequence (repeat the previous sequence), iii) and the range of probes that compose the barcodes (i.e. 1-25, 26-50) based on the number of oligos in each barcode. Information i) to iii) must be separated with a Tab. Use the sequences from Supplementary Table 2.
CRITICAL STEP: The sequences must be given 5’ to 3’.
5. Use order.py to add the readout sequences. It will require the full list of oligos from step 3 and the list of readout sequences to add from step 4. 
6. Use order.py in interactive mode (-i) with the output file from last step to add the sequence of the universal priming region. Use sequences from Supplementary Table 3. 
CRITICAL STEP: It is possible to embed multiple libraries within one oligopool by using different sets of universal primers.
7. Order the microarray from an oligopool synthesizer company. 
CRITICAL STEP: Companies typically require two weeks to synthesize a custom-made oligopool. 

### Amplification of Oligopaints * Timing 4-5 days 

8. Emulsion PCR. This step is performed to amplify the starting oligopool (which can be limiting) in a non-biased manner. Set up a PCR Master Mix for each library as indicated in Table 1 and keep it on ice until needed. Pre-chill a 2-mL 11 mm glass vial in the freezer, place it on the center of a controlled stir plate and then add a pre-cooled stirring bar to the vial. Transfer 600 µL of PCR oil phase to the glass vial with a positive displacement pipette. Stir at 1000 rpm for at least 1 minute. While the stirring bar is still spinning, add 100 µL of PCR master mix in steps of  20 µL increments using a P20 pipette (i.e. dispense 20 µL 5 times). Stir at 1000 rpm for 10 minutes, the emulsion should appear milky white and foamy. Transfer the emulsion to a PCR strip tube (~8 x 75 µL) with a positive displacement pipette. 
CRITICAL STEP: Forward primer is the 5’ => 3’ forward universal priming sequence whereas reverse primer is the reverse complement of the reverse universal priming sequence.  
CRITICAL STEP: Emulsion preparation must be performed in a cold room at 4°C. All the equipment must be put there in advance to cool it down before use.
CRITICAL STEP: It would not be possible to transfer the whole emulsion volume to the PCR strip tube, quality over quantity here.

TABLE 1



9. Perform the PCR using the following cycling conditions:


| Cycle number | Denature | Anneal | Extend |
| ---- | ---- | --- | ---|
|1 | 95 °C, 2 min | |
|2-31 | 95 °C, 15 sec | 60 °C, 15 sec | 72 °C, 20 sec|
|32| | | 72 °C, 5 min |

PAUSE POINT: PCR product can be stored at 4 °C for a few days.

10. *Small scale emulsion PCR breaking.* Pool the emulsion PCR reactions in a 1.5 mL microcentrifuge tube. Add 1 µL of gel loading buffer to visualize the aqueous phase. Add 200 µL of mineral oil and vortex for 30 sec. Centrifuge at maximum speed for 10 min and remove the upper organic phase.
11. Add 1 mL of water-saturated diethyl ether and vortex for 1 min. Centrifuge at maximum speed for 1 min and remove the diethyl ether upper phase.
11. Add 1 mL of water-saturated ethyl acetate and vortex 1 for min. Centrifuge at maximum speed for 1 min and remove the ethyl acetate upper phase.
13.  Repeat step 11. Evaporate the residual diethyl ether by incubating the tube at 37 °C for 5 min with the cap open.CRITICAL STEP: The final volume should be around 80 µL.PAUSE POINT: PCR product can be stored at 4 °C for a few days.
14. *Purify the DNA by using Zymo Oligo Clean & Concentrator kit*. Mix 80 µL of DNA from the emulsion PCR breaking, 160 µL of oligo binding buffer and 320 µL of ethanol. Homogenize the solution by pipetting up and down 10 times. Follow the manufacturer’s instructions up to the DNA elution. Repeat elution with an extra 15 µL of water and then add 20 µL of water directly into the tube to obtain a final volume of 50 µL. 
15. Quantify DNA concentration using a NanoDrop by directly taking 2 µL of purified PCR product. Concentration should be between 20-40 ng/µL.
16. Run a gel electrophoresis to check for a single band amplification with 200 ng of PCR product in a 1.5 % agarose gel with 0.01% SYBR Safe at 100 V for 45 min.? TROUBLESHOOTINGPAUSE POINT: Purified products can be frozen at -20 °C for several months.
    Perform the small scale limited-cycle PCR by setting up the following reaction mix for 8 tubes as indicated in Table 2. CRITICAL STEP: The limited number of cycles is done to find the cycle number where the PCR is still at is exponential phase (Fig. 2c). 
17. Perform this step before proceeding to the large-scale PCR.CRITICAL STEP: The T7 promoter sequence (5’-TAATACGACTCACTATAGGGT-3’) should be added to the reverse primer used for the emulsion PCR step to allow for the reverse transcription step. 

**Table 2. Small scale limited-cycle PCR set-up.**

18. Run the following PCR program. Pick up the corresponding tube after each of the cycles 8-15 just after the extension phase. To do so, quickly open the PCR machine, remove the corresponding tube, close the lid and resume program.
PAUSE POINT: PCR product can be left overnight (ON) at 4°C or frozen for up to a month at -20°C .

| Cycle number | Denature | Anneal | Extend |
| ---- | ---- | --- | ---|
| 1 | 95 °C, 5 min | | |
| 2-15 | 95 °C, 30 sec | 60 °C, 45 sec | 72 °C, 30 sec |

19. Run 20 µL of the PCR product in a 1.5 % agarose gel with 0.01% SYBR Safe at 100 V for 45 min. Find the cycle with a single band of the expected size and the maximum intensity (Fig. 2c). 
20. Perform a large scale limited-cycle PCR by running a reaction mix for 16 tubes as indicated in Table 3. This step will generate a big quantity of Oligopaints. 
CRITICAL STEP: The T7 promoter sequence should be added to the reverse primer to allow for the reverse transcription step.

** Table 3. Large scale limited-cycle PCR mix.	 	 	** 	 	 	

21. Split the volume of the mix in Table 3 into 16 x 50 µL PCR tubes and run the PCR program from step 18 using the optimized number of cycles determined in step 19. Add a last extension cycle of 5 min at 72 °C.
PAUSE POINT: PCR product can be safely stored for months at -20°C.
22. Run 20 µL of the PCR product in an agarose gel as in step 16  to check that the PCR was successful.
? TROUBLESHOOTING 
23. Collect the 50 µL-aliquots from the previous step in a 15 mL falcon tube and proceed to DNA column purification according to the manufacturer's instructions.
CRITICAL STEP: Use Zymo DNA purification kit with  25 µg capacity. Elute using 30 µL of DNAse- and RNAse-free water.
24. Quantify product concentration with a NanoDrop using double-stranded DNA parameters. This typically requires a 1/10 dilution of a 2 µL aliquot of the purified product. Concentration should be between 30-50 ng/µL.
25. Run the reminder of the 1/10 stock dilution in a 1.5 % agarose gel as in step 16 (Fig. 2d).
CRITICAL: Check for a single band of the expected size.
26. Perform in vitro transcription by setting up the reaction mix as indicated in Table 4.
CRITICAL STEP: This step is a high-yield reaction that further amplifies the template molecules as well as converts them into RNA. It is necessary to keep RNAse-free conditions at all times.
? TROUBLESHOOTING

** Table 4. In vitro transcription solution mix.	 	 **	 	 	 	

27. Split the volume from the in vitro transcription solution into 3x20 µL PCR tubes and incubate at 37 °C for 12-16 h in a thermocycler.
PAUSE POINT: In vitro transcription product can frozen for months at -80°C.
28. Take 5 µL and purify with a Zymo Oligo Clean & Concentrator kit according to manufacturer’s instructions, using 15 µL of DNAse and RNAse-free water to elute purified product.
CRITICAL STEP: The purification is only performed with a small aliquot to control if the in vitro transcription was successful and to estimate the RNA concentration in the non-purified RNA solution. Use Zymo DNA purification kit with 10 µg capacity. 
29. Make a 1/10 dilution to perform a quantification of the purified RNA on NanoDrop using RNA parameters. Concentration should be between 0.5-2 µg/µL.
CRITICAL STEP: The concentration obtained allows to estimate concentration in non-purified RNA. For example, a 2 µg/µL concentration in the purified RNA can be translated to an estimated concentration of 6 µg/µL in the non-purified RNA considering a factor 3 dilution (from a 5 µL aliquot to a final volume of 15 µL). The total yield of the in vitro transcription step should be around 150-450 µg from a single transcription step (60 µL in total).
30. Check for the RNA quality by Urea PAGE (Fig. 2e). Perform a pre-run for 30 min in 1X TBE at 190 V to eliminate the excess of persulfate. When finished, wash the wells with the running buffer. Load 100 ng of purified RNA per lane. Heat the samples at 95 °C for 5 min and put it immediately on ice for 2 min. Perform the PAGE for 1 h at 190 V. For gel staining, incubate protected from light for 20 min in 30 mL of TBE 1X and 3 µL of SyBR Gold. 
31. Perform the reverse transcription reaction according to Maxima H Reverse Transcriptase kit by setting up the reaction mix indicated in Table 5.
CRITICAL STEP: In this step, the non-purified RNA from step 27 is directly used. RNA should always be kept in ice to prevent degradation.
CRITICAL STEP: Primer sequence is the same as for forward primer used in emulsion PCR or limited-cycle PCR.

**Table 5. Reverse transcription mix.	 	** 	 	 	 	

32. Split the volume obtained in the previous step into two 1.5 mL tubes and incubate for 3 h at 50 °C in a water bath.
PAUSE POINT: Reverse transcription product can frozen for months at -20°C.
33. Perform the RNA degradation by adding into each tube 300 µL of 0.5 M EDTA and 300 µL of 1 M NaOH and incubating at 95 °C for 15 min in a water bath.
CRITICAL  STEP: This step allows to selectively degrade the RNA while keeping single stranded DNA.
34. Take a 10 µL aliquot to control for DNA concentration and to perform a gel electrophoresis as in step 16.
35. DNA probe purification. Mix the 2 aliquots in a sterile 50-mL Falcon tube. Add 4.8 mL of oligo binding buffer and 19.2 mL of ethanol. Homogenize and spread over two columns. Follow the manufacturer’s instructions from this point on. 
CRITICAL STEP: Use the Zymo DNA purification kit with 100 µg capacity.
36. Take a 10 µL aliquot to measure DNA concentration  and to perform a gel electrophoresis as in step 16. 
37. Ethanol precipitation. Directly add to the  150 µL DNA elution, 24 µL of 5 M ammonium acetate, 6 µL of glycogen and 750 µL of 100% (v/v) ethanol at -20°C. Vortex and incubate 1 h at -80°C. Centrifuge at 13,000G for 1 h at 4°C. Discard the supernatant and wash the pellet with 1 mL of ice-cold 70% ethanol (v/v). Centrifuge at 13,000G for 15 min at 4°C. Discard the supernatant and add 20 µL of DNase- and RNase-free water. Let the single stranded DNA (ssDNA) resuspend for 10 min at 37°C. Keep on ice.
38. Quantify oligo concentration with a NanoDrop using ssDNA parameters. 
CRITICAL: Total quantity of ssDNA should be in the order of 80-120 µg.
39. Control the quality of ssDNA by Urea PAGE as in step 30 (Fig. 2e).
CRITICAL STEP: This step allows to verify RNA degradation and the efficacy of reverse transcription step.
PAUSE POINT: Probes can be stored at -20 °C for months.

### Embryo collection and fixation  * Timing 2-3 h 

40. Place 200–400 flies with a 2:1 female/male ratio into an egg-collection cage mounted with an apple juice plate containing a dollop of yeast paste and prewarmed to 25 °C (or the temperature required for the specific experiment). Perform an ON pre-laying step.
41. Replace the plate with a new one containing a dollop of yeast paste and prewarmed to 25 °C. Perform a laying step during 1.5 h at  25 °C.
42. Remove the plate, put the cover and incubate 1 h (or the time required to obtain embryos in the desired developmental stage) at  25 °C.
43. Rinse the plates with ddH2O and carefully detach embryos using a brush. Filter the liquid using a nylon filter. Embryos will remain on it. 
44. Prepare a six well plate with one well containing bleach at 2.6% active chlorine, and the other five containing water. Put the filter with the embryos in the bleach containing well and incubate for 5 min.
45. Rinse sequentially the embryos by immersing the nylon filter into the water-containing wells. Dry them in between steps by pressing on a paper tissue. Place the embryos at the center of the filter.
46. Using a 1 mL pipet, add 5 mL of 4% (v/v) formaldehyde in PBS to rinse the filter and displace embryos into a 20-mL glass vial.
! CAUTION Formaldehyde is toxic and should be handled with protective gloves under a fume hood and discarded according to the relevant environmental and safety instructions.
47. Add 5 mL of heptane to the vial, close and vigorously shake it manually  during 30 sec. You may cover the cap of the vial with parafilm to avoid leakage of the formaldehyde and heptane solution inside. Incubate the embryos during 20 minutes at RT.
48. Aspirate the lower aqueous phase on the bottom of the vial using a glass Pasteur pipet.
! CAUTION Formaldehyde is toxic and should be handled with protective gloves under a fume hood and discarded according to the relevant environmental and safety instructions.
49. Add 5 mL of methanol and vortex the glass vial during 15 seconds. Using a glass Pasteur pipet, transfer the embryos at the bottom of the glass vial to a 1.5 mL tube. 
! CAUTION Methanol is toxic and highly volatile and should be handled with protective gloves under a fume hood and discarded according to the relevant environmental and safety instructions.
CRITICAL STEP: Glass pipet is used to avoid embryos attaching to the walls. Avoid using plastic tips.
50. Wash the embryos three times with 1 mL of  methanol.
PAUSE POINT: Fixed embryos can be stored in methanol at -20°C for months.

### RNA  in situ hybridization  * Timing 2.5 days
