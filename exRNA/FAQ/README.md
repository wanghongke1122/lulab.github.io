# FAQ for exRNA

* TOC
{:toc}
---
---
## General

#### What is PBMC?

**Answer:** **Human Peripheral Blood Mononuclear Cells (PBMCs)** are blood cells with a single round nucleus. These cells include lymphocytes (T, B and NK cells), monocytes and dendritic cells.  PBMCs are parts of the immune system which are critical to cell-mediated and humoral immunity.
Our Human PBMCs are isolated from normal healthy donor leukopaks collected in acid-citrate-dextrose formula A (ACDA) as an anticoagulant. All donors must be tested negative for HBV, HCV and HIV and are IRB consented.

![PBMC](img/PBMC.jpeg)

## exRNA: extra-cellular RNA

#### How many types of exRNAs?

**Answer:** **exRNA** (extra-cellular RNA) includes long and short RNAs, which can be derived from the whole plamsa/serum (**cf-RNA**: cell -free RNA), or enriched from the exosomes/EVs of plasma/serum (**exoRNA**).

* *Long RNA* (>200nt): mRNA (RNA coding for protein), lncRNA (long noncoding RNA), rRNA
* *Small noncoding RNA (ncRNA)* (20-30nt): miRNA, piRNA, siRNA
* *Ohter noncoding RNA (ncRNA)* (100-200nt): tRNA, Y RNA, snRNA, snoRNA, srp RNA, etc

 

## RNA-seq

#### What is barcode and multiplex?

**Answer:** Multiplex sequencing allows large numbers of libraries to be pooled and sequenced simultaneously during a single run on a high-throughput instrument. Sample multiplexing is useful for many applications, from targeted panels to whole human genome sequencing.

Individual "barcode" sequences are added to each DNA fragment during next-generation sequencing (NGS) library preparation so that each read can be identified and sorted before the final data analysis. Pooling samples exponentially increases the number of samples analyzed in a single run, without drastically increasing cost or time.

> Multiplex Sequencing Highlights

- *Fast High-Throughput Strategy:* Large sample numbers can be simultaneously sequenced during a single experiment
- *Cost-Effective Method:* Sample pooling improves productivity by reducing time and reagent use
- *High-Quality Data:* Accurate maintenance of read length of unknown sequences
- *Simplified Analysis:* Automatic sample identification with "barcodes" using Illumina data analysis software

![barcoding](img/barcoding.jpg)


#### What is SMARTer?
**Answer:** Switch Mechanism at the 5' End of RNA Templates, which relies on template switching, used for transcriptome analysis from single cells. Smart-Seq was developed as a single-cell sequencing protocol with improved read coverage across transcripts. 

Procedure: Cells are lysed, and the RNA is hybridized to an oligo(dT)-containing primer. The first strand of the cDNA is synthesized with the addition of a few untemplated C nucleotides. This poly(C) overhang is added exclusively to full-length transcripts. An oligonucleotide primer is hybridized to the poly(C) overhang and used to synthesize the second strand. Full-length cDNAs are PCR-amplified to obtain nanogram amounts of DNA. The PCR products are purified for sequencing.

There are 2 versions of Smart-Seq: Smart-Seq and Smart-seq2. Smart-seq2 includes several improvements over the original Smart-Seq protocol. The new protocol includes a locked nucleic acid (LNA), an increased MgCl2 concentration, betaine, and elimination of the purification step to improve the yield significantly.

![SMARTer](img/SMARTer.png)

> Reference:

- [Picelli, S., Faridani, O. R., Björklund, Å. K., Winberg, G., Sagasser, S., & Sandberg, R. (2014). Full-length RNA-seq from single cells using Smart-seq2. Nature protocols, 9(1), 171.](https://www.ncbi.nlm.nih.gov/pubmed/24385147/)


#### What is TSO?

**Answer:** The TSO (template switch oligo) is an oligo that hybridizes to untemplated C nucleotides added by the reverse transcriptase during reverse transcription. The TSO adds a common 5' sequence to full length cDNA that is used for downstream cDNA amplification.

The TSO is used differently in the Single Cell 3' assay compared to the Single Cell 5' assay. In the 3' assay, the polyd(T) sequence is part of the gel bead oligo (which also contains the 10x Barcode, UMI, and partial Illumina Read 1 sequence), with the TSO supplied in the RT Primer. In the 5' assay, the polyd(T) is supplied in the RT Primer, and the TSO is part of the gel bead oligo.


Single Cell 3' assay after reverse transcription:


![TSO-3](img/TSO-3.png)

 

Single Cell 5' assay after reverse transcription:

![TSP-5](img/TSO-5.png)

Products: Single Cell 3', VDJ


> [Original Page](https://kb.10xgenomics.com/hc/en-us/articles/360001493051-What-is-a-template-switch-oligo-TSO-)



#### What is UMI?

**Answer:** Unique molecular identifiers (UMI) are molecular tags that are used to detect and quantify unique mRNA transcripts. In this method, mRNA libraries are generated by fragmentation and reverse-transcribed to cDNA. Oligo(dT) primers with specific sequencing linkers are added to the cDNA. Another sequencing linker with a 10 bp random label and an index sequence is added to the 5' end of the template, which is amplified and sequenced. Sequencing allows for high-resolution reads, enabling accurate detection of true variants.

> Pros:

- Can sequence unique mRNA transcripts
- Can detect transcripts occurring at low frequencies
- Transcripts can be quantified based on sequencing reads specific to each barcode
- Can be applied to multiple platforms to karyotype chromosomes

> Cons:

- Targets smaller than 500 bp are preferentially amplified by polymerases during PCR

> Reference:

- [Kivioja T., Vaharautio A., Karlsson K., Bonke M., Enge M., et al. (2012) Counting absolute numbers of molecules using unique molecular identifiers. Nat Methods 9: 72-74](http://www.ncbi.nlm.nih.gov/pubmed/22101854)

  

![UMI](img/umi.png)



#### What is DASH/CRISPR?

**Answer:** DASH means Depletion of Abundant Sequences by Hybridization. Sequencing libraries are ‘DASHed’ with recombinant Cas9 protein complexed with a library of guide RNAs targeting unwanted species for cleavage, thus preventing them from consuming sequencing space. Depletes abundant species after complementary DNA (cDNA) amplification, and thus can be utilized for essentially any amount of input sample.


> Reference:

- [Gu, W., Crawford, E. D., O’Donovan, B. D., Wilson, M. R., Chow, E. D., Retallack, H., & DeRisi, J. L. (2016). Depletion of Abundant Sequences by Hybridization (DASH): using Cas9 to remove unwanted high-abundance species in sequencing libraries and molecular counting applications. Genome biology, 17(1), 41.](https://www.ncbi.nlm.nih.gov/pubmed/26944702)
