Overview
==========
This is a pipeline for the CEL-Seq method.
CEL-Seq is a HTS method published hashimshony et. al(2012), based on RNAseq. 
It typcially reads only the 3'UTR end of mRNA transcripts and is stranded.

The pipeline input is paired-end read files (FASTQ format,) alongside a reference genome and annotation and outputs a read count.

Complete workflow
=================
To use the pipeline completely, you need to create a config file (use the
`config_file_example.txt` as an example). The config file tells the pipeline
what are the required actions on which files, and references the references.

The invocation is:

    pijpleiding config_file.txt

Useful scripts
==============
Two of the scripts are useful also without the complete pipeline.

bc_demultiplex
--------------
A CELSeq demultiplexer, to demultiplex the CELSeq barcodes. It also
saves UMI information with the reads.

Use `bc_demultiplex --help` to understand the input format.

htseq_count_umified
-------------------
An adapation of the `htseq_count` script from the `HTSeq` package,
to count each UMI only once,
based on the UMI information from `bc_demultiplex`.


Dependencies
==============
General: bowtie2, python2.7
Python packages: [HTSeq](https://pypi.python.org/pypi/HTSeq)

