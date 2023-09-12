# The goal of this work was to search for histone modifications using ChIP-Seq data analysis.

[This README in russian](README.ru.md)

All operations were performed in the Linux terminal after downloading the data from [here](https://www.encodeproject.org/chip-seq-matrix/?type=Experiment&replicates.library.biosample.donor.organism.scientific_name=Homo%20sapiens&assay_title=Histone%20ChIP-seq&assay_title=Mint-ChIP-seq&status=released).  
All commands are in .docx files (proof folder).

For this analysis were taken human fibroblast sequencing data (GM23248) for the histone mark H3K4me1.  
Samples ENCFF182AFY and ENCFF335CQJ were analyzed against the control ENCFF569WIS.  

Since FastQC output was within normal limits, I did not perform filtering.

The sequences were aligned to chromosome 14.  
Alignment statistics:
|  | ENCFF182AFY | ENCFF335CQJ | ENCFF569WIS |
| --- | --- | --- | --- |
| Number of reads | 36 622 019 | 37 314 930 | 47 833 064 |
| Uniquely aligned | 1 453 730 (3.97%) | 1 496 129 (4.01%) | 2 039 214 (4.26%) |
| Not uniquely aligned  | 2 408 769 (6.58%) | 2 601 874 (6.97%) | 4 203 710 (8.79%) |
| Not aligned | 32 759 520 (89.45%) | 33 216 927 (89.02%) | 41 590 140 (86.95%) |

As can be seen, most of the sequences were not mapped. This is probably due to the fact that only chromosome 14 was taken; the remaining reads are from other parts of the genome.  
Here it was possible to select unique mapped reads and convert .sam files to binary format, but I did not do this.  

The resulting peaks were compared with ones in ENCODE
Сравниваем те пики, которые мы получили, с пиками, которые приведены в ENCODE (важно, чтобы версии генома hg38 или hg19) для .bed файла из ENCODE и той хромосомы, которую скачивали выше, сопадали.
Проанализируйте полученные результаты и приведите свои рассуждения в README.md. Как можно объяснить различия в количестве пересечений?

Полученные диаграммы Венна находятся в папке Intervene. В обоих случаях больше пиковых последовательностей получается при наложении полученного файла на файл .bed из базы ENCODE (ENCFF806LPY). Возможно, средняя длина наших последовательностей получилась короче за счёт не уникально закартированных ридов. 
