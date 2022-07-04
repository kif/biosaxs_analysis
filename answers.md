Dear Co-Editor,

Please find hereafter our answers to the three referees:

# Referee 1
1. The document was proof-read by Mark Tully, co-author, who is a native English speaker.
2. This refers actually to the command line tool (all lower case), different from the project which is named FreeSAS and includes it. We descided to use a monospaced font to better distinguish the name of the program from the project. 
3. Fixed, thanks for spotting it
4. Distinction between IFT, the BIFT algorithm and the name of the program was made clearer (using monospaaced font).
5. This section reshuffled with a table 1 listing all applications.
6. Main text updated to avoid the issue
7. Figure updated to avoid having two stage 2
8. The sentence has been dropped.
9. A sentence was added to compare the performances with the previous setup
10. The full sentence was removed. Just to comment on the reliability: Dahu is running as a single program with threads running algorithms implemented by FreeSAS using Cython. Any memory management error within the Cython part would crash the complete server. Since this does not occur, it proves the ensemble is reliable, unfortunately it does not prove all the math were properly implemented.
11. Experimental conditions updated
# Referee 2
0. This document is about fully automated pipelines for the reduction of BioSAXS data, it is thus normal there is not user interface. In the future, it is foreseen that the user can reprocess data with slightly different parameters from the ISPyB web-interface, but this is not yet done. An advanced user may rather start playing with FreeSAS because it is ESRF-independent and easy to deploy anywhere, unlike the pipelines which are heavily optimized for the local infrastructure (Manuscrip updated accordingly). While all structures should end in the SASBDB, the work presented here aims only at providing user with a DOI associated with their data, that they can easily link when uploading to the SASBDB, in a similar way to:https://www.panosc.eu/use-cases/panosc-use-case-10-linking-raw-data-to-the-protein-data-bank-in-europe-pdbe/
1. Done
2. The different pipelines presented are closely bound to the beamline and are not directly usable elsewhere, this is why the SAS related part is made available in FreeSAS.
3. If one considers reduction stops at the subtraction of background, the pipeline is actually providing data analysis (Guinier, Porod, Kratky and IFT)
4. The version of ATSAS which are cited are the one which used to be in the former pipeline (and thus no more used, i.e. versions 2.4 to 2.6). There is no point here in citing the latest publication about ATSAS.
5. The limiting factor were related to the structure of EDNA (not to ATSAS) and was clearly stated  (page7 l18), but on page 2, we are still in the introduction. ATSAS was dropped mainly because of maintenance issues. 
6. Done
7. p2l67: The code has been designed to perform up to 10fps. But similar processing pipelines are handling 100 fps at ESRF and the new serial-crystallography beamline is foreseen to operate at 1000 fps using similar code. Performances of the underlying code is available at http://www.silx.org/doc/pyFAI/latest/performance.html A complete discussion can be found in https://dx.doi.org/10.1107/S1600577518000607
8. p3l22: This pipeline has been tailored for the BioSAXS beamline. Similar pipelines are in use at the TruSAXS beamline (ID02) where experiments are more time-resolved and stop-flow. https://doi.org/10.1107/S1600576721012693
9. p3l33 Put references to the "performances" section
10. p3l57: Link to comparison added.
11. p4l25: Fixed
12. p4l62: Caption updated
13. p5l62: Changed words to be more accessible to biologists
14. p6: Table 1 was added to be more explicit.
15. p7: Reference to SLURM was added and the reason for not using it was given
16. p8: Sentence reformulated
17. p11l10: Yes, for sure this approach is much slower, but we since the processing time is still within specification, this is not too much of an issue. Moreover a fast and correct pathway exists and it could easily be implemented when needed. The complete demonstration would deserve a publication on its own but since the difference is subtle (at best, nonexistent most of the time) few people actually care about this (private communication with Brian Pauw).
18. p11l58: Each of the pipeline start when triggered, thus in HPLC mode, the chromatogram appears only at the end since it is triggered after the last frame has been acquired. Partial feed-back is given to the user after each block of 100 frames got processed (this is a limitation related to HDF5 since the SWMR feature cannot be implemented at this beamline, this would require modification of the network of the beam-line which is not justified with so little throughput.)
19. p14: Explained
20. p18 No, manual peak-picking is not allowed. Background subtracted curves are produced and made available thus the user who can average by hand any region he likes in post-processing.
21. p19: For now, the ISPyB for Biosaxs database is not suited for the current analysis pipeline. Those pipelines have to export data in a similar way to former EDNA based pipelines and many features are lost. The short term project is rather to provide more information via the data-portal since it features already already a HDF5 web-viewer. The current upgrade of ISPyB is rather centered on serial-crystallography than on biosaxs.
22. p20l28 you are right
23. FAIR has been introduced earlier
24. Method has been updated accordingly.

# Referee 3
1. You are right, since all software is new, this is not an upgrade but a new development. Text has been adapted.
2. Done
3. Reformulated
4. Figure updated accordingly
5. I was not aware of NMF being used in SEC-SAXS despite the technique is now standard in spectroscopy (implemented in PyMca for example). BioXTAS-RAW is to our knowledge the most advanced software doing multivariate analysis, but it does not implement NMF. There is a reference, found in the SASBDB where NMF was used to extract components. It has been cited.  
6. Done
7. Done
8. You are right, the average is also wrong when using an arithmetic average, but the deviation is more easily visible in the propagated uncertainties than in the signal.
9. The normalization factor, originating from the integrated beam-stop diode intensity, can vary greatly from one frame to another. On the TruSAXS beam-line (ID02) where they have dedicated hardware to program the sequence of exposure time, this is very common. On the BioSAXS beam-line (BM29), acquisition are performed with constant exposure time but refill of the storage ring can occur during an acquisition (+50% flux when in 4- or 16-bunch mode) and when this occurs, normalisation factor are far from being constant. Nevertheless the beam-line is rarely receiving user-experiment during those exotic filling mode.
10. About the discussion about the order of averaging/integrating. This has already been presented in https://doi.org/10.1107/S1600577520000776 equation 5, and I can confirm you there is no technical issue in implementing it.
11. Several performance comparison with the former pipeline have been added. One would like to point, the EDNA based pipeline was slow because of the internal structure of EDNA, not because it was using ATSAS !
12. Typos addressed
