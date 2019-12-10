## Haphpipe -- Bioinformatics Research Project

---

### Basic

Haphpipe is a HAplotype and PHylodynamics pipeline for viral assembly, population genetics, and phylodynamic.
We will be introducing the Haphpipe software created by Computational Biology Institute at the George Washington University. 
Keylie Gibson from Computational Biology Institute at the George Washington University recruited us to work from the ground up with the program and create a guide that is more accessible and easily understood to those that have not used such a program before. 
---
### haphpipe_assemble_01

```
haphpipe_assemble_01 read1.fq.gz read2.fq.gz HIV_B.K03455.HXB2.fasta HIV_B.K03455.HXB2.gtf sampleID
```
This pipeline implements denovo assembly. Reads are first trimmed (trim_reads) and used as input for denovo assembly (assemble_denovo). The denovo assembly stage automatically performs error detection, but trimmed reads are also error corrected (ec_reads). The assembled contigs are used as input for amplicon assembly (assemble_amplicons) along with reference FASTA and GTF files. The assembly is then iteratively refined up to five times (refine_assembly) by mapping corrected reads to the assembled FASTA file and lastly finalized (finalize_assembly), resulting in a FASTA file with final consensus sequences, final VCF, and aligned BAM file.

<img src="images/hp01.png?raw=true"/>

---
### haphpipe_assemble_02

```
haphpipe_assemble_02 read1.fq.gz read2.fq.gz HIV_B.K03455.HXB2.amplicons.fasta sampleID
```
This pipeline implements reference-based mapping assembly. Reads are first trimmed (trim_reads) and error-corrected (ec_reads). The corrected reads are used as input for reference-based mapping assembly (refine_assembly) for up to five iterations. Lastly, the assembly is finalized (finalize_assembly) by mapping reads onto the refined reference sequence. The final output is a FASTA file with final consensus sequences, final VCF, and aligned BAM file.
---

<p style="font-size:11px">Page template forked from <a href="https://github.com/evanca/quick-portfolio">evanca</a></p>
<!-- Remove above link if you don't want to attibute -->
