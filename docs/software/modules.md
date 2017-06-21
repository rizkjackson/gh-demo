
<!--
WARNING: do _not_ update this file; it is automatically generated from modules.md.rsp and will be overwritten.
-->

<div class="alert alert-warning" role="alert">
Environment modules are currently in beta - to enable them, see Configuration / <a href="{{ '/configuration/lmod.html' | relative_url }}">Enable Software Modules</a>.
</div>

# Software

To use one or more of the below software modules, use `module load <name>` or `module load <name>/<version>`.  Here are a few examples:
```sh
module load bowtie2
module load bowtie2/2.2.6
module load python r bwa
```


## Modules

_The below information was automatically generated on 2017-06-20 12:41:28._


### Module Repository 'CBC'

Location: `MODULEPATH=$MODULEPATH_ROOT/CBC`

<table>
 <tr>
  <th>name &amp; versions</th>
  <th>description</th>
 </tr>
 <tr>
  <td>
  <strong>anaconda</strong><br>
  N/A
  </td>
  <td>
  <strong>Anaconda Package Manager w/ CBC-shared installations</strong><br>
  Open Data Science Platform powered by Python<br>
  URL: <a href="https://www.continuum.io/anaconda-overview">https://www.continuum.io/anaconda-overview</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>anaconda-python</strong><br>
  2.7.13
  </td>
  <td>
  <strong>Anaconda: The Python Programming Language</strong><br>
  The Python programming language (by Anaconda)<br>
  URL: <a href="https://www.python.org/">https://www.python.org/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>bamutil</strong><br>
  1.0.14
  </td>
  <td>
  <strong>BamUtil - programs for working on SAM/BAM files</strong><br>
  bamUtil is a repository that contains several programs that perform operations on SAM/BAM files. All of these programs are built into a single executable, bam.<br>
  URL: <a href="http://genome.sph.umich.edu/wiki/BamUtil">http://genome.sph.umich.edu/wiki/BamUtil</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>bcftools</strong><br>
  1.2, 1.3.1, 1.4
  </td>
  <td>
  <strong>BCFtools: utilities for variant calling and manipulating VCFs and BCFs</strong><br>
  BCFtools is a set of utilities that manipulate variant calls in the Variant Call Format (VCF) and its binary counterpart BCF. All commands work transparently with both VCFs and BCFs, both uncompressed and BGZF-compressed.<br>
  URL: <a href="https://samtools.github.io/bcftools/bcftools.html">https://samtools.github.io/bcftools/bcftools.html</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>bedops</strong><br>
  1.2.2c
  </td>
  <td>
  <strong>BEDOPS: the fast, highly scalable and easily-parallelizable genome analysis toolkit</strong><br>
  BEDOPS is an open-source command-line toolkit that performs highly efficient and scalable Boolean and other set operations, statistical calculations, archiving, conversion and other management of genomic data of arbitrary scale. Tasks can be easily split by chromosome for distributing whole-genome analyses across a computational cluster.<br>
  URL: <a href="https://bedops.readthedocs.io/">https://bedops.readthedocs.io/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>bedtools2</strong><br>
  2.13.4, 2.15.0, 2.16.2, 2.26.0
  </td>
  <td>
  <strong>Bedtools2</strong><br>
  Collectively, the bedtools utilities are a swiss-army knife of tools for a wide-range of genomics analysis tasks. The most widely-used tools enable genome arithmetic: that is, set theory on the genome. For example, bedtools allows one to intersect, merge, count, complement, and shuffle genomic intervals from multiple files in widely-used genomic file formats such as BAM, BED, GFF/GTF, VCF.<br>
  URL: <a href="https://github.com/arq5x/bedtools2/">https://github.com/arq5x/bedtools2/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>blast</strong><br>
  2.2.26
  </td>
  <td>
  <strong>BLAST: Basic Local Alignment Search Tool</strong><br>
  BLAST finds regions of similarity between biological sequences. The program compares nucleotide or protein	sequences to sequence databases and calculates the statistical significance.<br>
  URL: <a href="https://blast.ncbi.nlm.nih.gov/Blast.cgi">https://blast.ncbi.nlm.nih.gov/Blast.cgi</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>bowtie2</strong><br>
  2.0.0-beta6, 2.1.0, 2.2.6, 2.2.9
  </td>
  <td>
  <strong>Bowtie2</strong><br>
  Bowtie 2 is an ultrafast and memory-efficient tool for aligning sequencing reads to long reference sequences.<br>
  URL: <a href="http://bowtie-bio.sourceforge.net/bowtie2/index.shtml">http://bowtie-bio.sourceforge.net/bowtie2/index.shtml</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>bwa</strong><br>
  0.5.10, 0.6.1, 0.7.12, 0.7.5a
  </td>
  <td>
  <strong>Burrows-Wheeler Aligner (BWA)</strong><br>
  Burrows-Wheeler Aligner (BWA) is a software package for mapping low-divergent sequences against a large reference genome, such as the human genome.<br>
  URL: <a href="http://bio-bwa.sourceforge.net/">http://bio-bwa.sourceforge.net/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>cbc-bin</strong><br>
  0.1.0
  </td>
  <td>
  <strong>CBC-shared Scripts and Binaries</strong><br>
  Utility scripts and binaries of the UCSF CBC group.<br>
  URL: <a href="https://cbc.ucsf.edu/">https://cbc.ucsf.edu/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>cbc-devel</strong><br>
  0.1.0
  </td>
  <td>
  <strong>CBC-shared Developer's Environment</strong><br>
  Setup for building and installing software inline with the CBC-shared setup.<br>
  URL: <a href="https://cbc.ucsf.edu/">https://cbc.ucsf.edu/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>cbc-shared</strong><br>
  0.1.0, 0.1.1, 0.1.2
  </td>
  <td>
  <strong>CBC-shared Software: Default Set</strong><br>
  When loaded, this module loads the default set of CBC-shared software.<br>
  URL: <a href="https://github.com/UCSF-TI/TIPCC/wiki/Software-shared-by-CBC">https://github.com/UCSF-TI/TIPCC/wiki/Software-shared-by-CBC</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>control-freec</strong><br>
  2.5, 7.2-3
  </td>
  <td>
  <strong>Control FREEC: Control-FREE Copy Number and Genotype Caller</strong><br>
  Prediction of copy numbers and allelic content using deep-sequencing data.<br>
  URL: <a href="http://boevalab.com/FREEC/">http://boevalab.com/FREEC/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>cufflinks</strong><br>
  1.0.3, 1.3.0
  </td>
  <td>
  <strong>Cufflinks: Transcriptome assembly and differential expression analysis for RNA-Seq</strong><br>
  Cufflinks assembles transcripts, estimates their abundances, and tests for differential expression and regulation in RNA-Seq samples. It accepts aligned RNA-Seq reads and assembles the alignments into a parsimonious set of transcripts. Cufflinks then estimates the relative abundances of these transcripts based on how many reads support each one, taking into account biases in library preparation protocols.<br>
  URL: <a href="http://cole-trapnell-lab.github.io/cufflinks/">http://cole-trapnell-lab.github.io/cufflinks/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>example</strong><br>
  0.1
  </td>
  <td>
  <strong>"This is an example of a basic Lua Module files"</strong><br>
  Example of Lua Module files<br>
  URL: <a href="http://content.allinea.com/downloads/userguide.pdf">http://content.allinea.com/downloads/userguide.pdf</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>fastqc</strong><br>
  0.10.1, 0.11.2
  </td>
  <td>
  <strong>FastQC</strong><br>
  A quality control tool for high throughput sequence data.<br>
  URL: <a href="http://www.bioinformatics.babraham.ac.uk/projects/fastqc/">http://www.bioinformatics.babraham.ac.uk/projects/fastqc/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>fiji</strong><br>
  2.0.0-rc-54
  </td>
  <td>
  <strong></strong><br>
  Fiji is a distribution of ImageJ which includes many useful plugins contributed by the community.<br>
  URL: <a href="https://imagej.net/Fiji/Downloads">https://imagej.net/Fiji/Downloads</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>gdc-client</strong><br>
  1.0.1
  </td>
  <td>
  <strong>GDC Data Transfer Tool</strong><br>
  The GDC provides a standard client-based mechanism in support of high performance data downloads and submission.<br>
  URL: <a href="https://gdc.cancer.gov/access-data/gdc-data-transfer-tool">https://gdc.cancer.gov/access-data/gdc-data-transfer-tool</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>genetorrent</strong><br>
  3.8.5a-94
  </td>
  <td>
  <strong>GeneTorrent</strong><br>
  GeneTorrent is a set of executables for accessing data in the Cancer Genomics Hub (CGHub), a secure repository for storing, cataloging, and accessing cancer genome sequences, alignments, and mutation information from the Cancer Genome Atlas (TCGA) consortium and related projects.<br>
  URL: <a href="https://hpc.nih.gov/apps/GeneTorrent.html">https://hpc.nih.gov/apps/GeneTorrent.html</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>git</strong><br>
  2.1.1, 2.1.3
  </td>
  <td>
  <strong>Git - Distributed Version Control System</strong><br>
  Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.<br>
  URL: <a href="https://git-scm.com/">https://git-scm.com/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>gitflow</strong><br>
  0.4.2
  </td>
  <td>
  <strong>Git extension Git Flow</strong><br>
  A collection of Git extensions to provide high-level repository operations for Vincent Driessen's branching model.<br>
  URL: <a href="https://github.com/nvie/gitflow">https://github.com/nvie/gitflow</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>htop</strong><br>
  1.0.3
  </td>
  <td>
  <strong>htop - an interactive process viewer for Unix</strong><br>
  htop is an interactive process viewer for Unix systems. It is a text-mode application (for console or X terminals) and requires ncurses.<br>
  URL: <a href="http://hisham.hm/htop/">http://hisham.hm/htop/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>htseq</strong><br>
  0.5.4p3, 0.6.1
  </td>
  <td>
  <strong>HTSeq: Analysing high-throughput sequencing data with Python</strong><br>
  HTSeq is a Python package that provides infrastructure to process data from high-throughput sequencing assays.<br>
  URL: <a href="http://www-huber.embl.de/users/anders/HTSeq/">http://www-huber.embl.de/users/anders/HTSeq/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>htslib</strong><br>
  1.3.2
  </td>
  <td>
  <strong>Samtools</strong><br>
  Samtools is a suite of programs for interacting with high-throughput sequencing data. It consists of three separate repositories: Samtools, BCFtools, and HTSlib.<br>
  URL: <a href="http://www.htslib.org/">http://www.htslib.org/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>igv</strong><br>
  2.1.2, 2.3.31, 2.3.68, 2.3.92
  </td>
  <td>
  <strong>IGV: The Integrative Genomics Viewer</strong><br>
  The Integrative Genomics Viewer (IGV) is a high-performance visualization tool for interactive exploration of large, integrated genomic datasets. It supports a wide variety of data types, including array-based and next-generation sequence data, and genomic annotations.<br>
  URL: <a href="https://software.broadinstitute.org/software/igv/">https://software.broadinstitute.org/software/igv/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>igvtools</strong><br>
  2.3.68, 2.3.91
  </td>
  <td>
  <strong>IGVTools</strong><br>
  The igvtools utility provides a set of tools for pre-processing data files.<br>
  URL: <a href="https://software.broadinstitute.org/software/igv/igvtools">https://software.broadinstitute.org/software/igv/igvtools</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>jdk</strong><br>
  1.6.0, 1.7.0, 1.8.0
  </td>
  <td>
  <strong>Java Development Kit (JDK)</strong><br>
  The Java programming language<br>
  URL: <a href="https://www.java.com/">https://www.java.com/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>lua</strong><br>
  5.1.4, 5.3.3
  </td>
  <td>
  <strong>The Lua Programming Language</strong><br>
  The Lua programming language<br>
  URL: <a href="https://www.lua.org/">https://www.lua.org/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>luarocks</strong><br>
  2.4.2
  </td>
  <td>
  <strong>LuaRocks - the Lua package manager</strong><br>
  LuaRocks is the package manager for Lua modules.<br>
  URL: <a href="https://luarocks.org/">https://luarocks.org/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>matlab</strong><br>
  R2010b, R2012a
  </td>
  <td>
  <strong>The Matlab Programming Language</strong><br>
  The Matlab programming language<br>
  URL: <a href="https://www.mathworks.com/products/matlab.html">https://www.mathworks.com/products/matlab.html</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>pandoc</strong><br>
  1.19.2-0
  </td>
  <td>
  <strong>Pandoc - a universal document converter</strong><br>
  Pandoc is a Haskell library for converting from one markup format to another, and a command-line tool that uses this library.<br>
  URL: <a href="http://pandoc.org/">http://pandoc.org/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>pip</strong><br>
  9.0.1
  </td>
  <td>
  <strong>pip - The PyPA recommended tool for installing Python packages</strong><br>
  The PyPA recommended tool for installing Python packages.<br>
  URL: <a href="https://pypi.python.org/pypi/pip">https://pypi.python.org/pypi/pip</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>python</strong><br>
  2.7.3, 2.7.4, 2.7.9
  </td>
  <td>
  <strong>The Python Programming Language</strong><br>
  The Python programming language<br>
  URL: <a href="https://www.python.org/">https://www.python.org/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>r</strong><br>
  2.11.0, 2.11.1, 2.12.2, 2.13.1, 2.13.2, 2.14.0, 2.15.0, 2.15.1, 2.15.2, 2.15.3, 3.0.0, 3.0.1, 3.0.2, 3.0.3, 3.1.0, 3.1.1, 3.1.2, 3.1.3, 3.2.0, 3.2.1, 3.2.2, 3.2.3, 3.2.4, 3.2.5, 3.3.0, 3.3.1, 3.3.2, 3.3.3, 3.3.3patched, 3.4.0, 3.4.0devel, 3.4.0patched, 3.5.0devel
  </td>
  <td>
  <strong>The R Programming Language</strong><br>
  The R programming language<br>
  URL: <a href="https://www.r-project.org/">https://www.r-project.org/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>r-extras</strong><br>
  0.1.0
  </td>
  <td>
  <strong>R Extras: Additional software, libraries and include paths needed to build some R / Bioconductor packages</strong><br>
  Additional software, libraries and include paths needed to build some R / Bioconductor packages<br>
  URL: NA<br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>s3cmd</strong><br>
  1.5.0-alpha3
  </td>
  <td>
  <strong>Amazon S3 Tools: Command Line S3 Client Software and S3 Backup</strong><br>
  ommand Line S3 Client and Backup for Linux and Mac<br>
  URL: <a href="http://s3tools.org/s3cmd">http://s3tools.org/s3cmd</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>samtools</strong><br>
  0.1.12a, 0.1.17, 0.1.18, 0.1.19, 0.1.19-patched, 1.2, 1.3.1
  </td>
  <td>
  <strong>Samtools</strong><br>
  Samtools is a suite of programs for interacting with high-throughput sequencing data. It consists of three separate repositories.<br>
  URL: <a href="http://www.htslib.org/">http://www.htslib.org/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>snpeff</strong><br>
  2_0_2
  </td>
  <td>
  <strong>SnpEff</strong><br>
  Genetic variant annotation and effect prediction toolbox.<br>
  URL: <a href="http://snpeff.sourceforge.net/">http://snpeff.sourceforge.net/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>snvmix2</strong><br>
  0.11.8-r3
  </td>
  <td>
  <strong>SNVMix2 - Detecting Single Nucleotide Variants from Next Generation Sequencing Data</strong><br>
  SNVMix is designed to detect single nucleotide variants from next generation sequencing data. SNVMix is a post-alignment tool.<br>
  URL: <a href="http://compbio.bccrc.ca/software/snvmix/">http://compbio.bccrc.ca/software/snvmix/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>sratoolkit</strong><br>
  2.3.4-2, 2.4.1, 2.5.7, 2.8.2-1
  </td>
  <td>
  <strong>SRA Toolkit</strong><br>
  The SRA Toolkit and SDK from NCBI is a collection of tools and libraries for using data in the INSDC Sequence Read Archives.<br>
  URL: <a href="http://ncbi.github.io/sra-tools/">http://ncbi.github.io/sra-tools/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>tophat</strong><br>
  1.3.0, 1.3.1, 1.4.0, 2.0.10, 2.0.3, 2.0.9, 2.1.0, 2.1.1
  </td>
  <td>
  <strong>TopHat</strong><br>
  TopHat is a fast splice junction mapper for RNA-Seq reads. It aligns RNA-Seq reads to mammalian-sized genomes using the ultra high-throughput short read aligner Bowtie, and then analyzes the mapping results to identify splice junctions between exons.<br>
  URL: <a href="https://ccb.jhu.edu/software/tophat/index.shtml">https://ccb.jhu.edu/software/tophat/index.shtml</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>udocker</strong><br>
  1.0.0
  </td>
  <td>
  <strong>udocker</strong><br>
  A basic user tool to execute simple containers in batch or interactive systems without root privileges.<br>
  URL: <a href="https://github.com/indigo-dc/udocker">https://github.com/indigo-dc/udocker</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>valgrind</strong><br>
  3.10.0, 3.8.1
  </td>
  <td>
  <strong>Valgrind - a programming tool for memory debugging, memory leak detection, and profiling</strong><br>
  Valgrind is a programming tool for memory debugging, memory leak detection, and profiling.<br>
  URL: <a href="http://www.valgrind.org/">http://www.valgrind.org/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>varscan</strong><br>
  2.2.3, 2.3.9
  </td>
  <td>
  <strong>VarScan</strong><br>
  Variant detection in massively parallel sequencing data<br>
  URL: <a href="http://dkoboldt.github.io/varscan/">http://dkoboldt.github.io/varscan/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>vcftools</strong><br>
  0.1.13
  </td>
  <td>
  <strong>VCFtools</strong><br>
  VCFtools is a program package designed for working with VCF files, such as those generated by the 1000 Genomes Project. The aim of VCFtools is to provide easily accessible methods for working with complex genetic variation data in the form of VCF files.<br>
  URL: <a href="https://vcftools.github.io/">https://vcftools.github.io/</a><br>
  </td>
 </tr>
 <tr>
  <td>
  <strong>wordspy</strong><br>
  1.5
  </td>
  <td>
  <strong>WordSpy</strong><br>
  A steganalysis-based approach to comprehensive identification and characterization of functional regulatory elements.<br>
  URL: <a href="http://cic.cs.wustl.edu/wordspy/dltemp.htm">http://cic.cs.wustl.edu/wordspy/dltemp.htm</a><br>
  </td>
 </tr>
</table>
