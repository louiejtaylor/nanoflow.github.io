## Nanopore Sequencing Analysis Tutorial

You can use the [editor on GitHub](https://github.com/zhaoc1/nanoflow.github.io/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Data set

First, create your `project_dir`:
  ```bash
  mkdir ~/nanoflow_tutorial
  ```
Second, we downloaed the long and short reads for sample INFO59 from [Ryan Wick's paper](https://www.ncbi.nlm.nih.gov/pubmed/29177090), which sequenced 12 Klebsiella pneumoniae on a single flow cell. We used [louiejtaylor](https://github.com/louiejtaylor)'s [grabseqs](https://github.com/louiejtaylor/grabseqs) to grab the sequencing data from SRA under theBioSample number SAMEA3357043.
  ```bash
  grabseqs sra -t 8 SAMEA3357043 -o ~/nanoflow_tutorial/01_basecalled_reads
  ```

There are three files in the `01_basecalled_reads` files:
- SRR5665596.fastq.gz: the Nanopore reads
- ERR1023792_1.fastq.gz: the Illumina forward reads
- ERR1023792_2.fastq.gz: the Illumina reverse reads

### Basecalling

Albacore is the data processig pipeline that provides the [Oxford Nanopore basecalling algorithms](https://nanoporetech.com/analyse), and several post-processing steps. In addition to Basecalling, Albacore also provided Barcoding/Demultiplexing. 
  ```bash
  read_fast5_basecaller.py --flowcell FLO-MIN106 --kit SQK-RBK001 --barcoding \
                           --output_format fast5,fastq --worker_threads 8 \
                           --recursive --input $raw_fast5_fp --save_path $basecalled_fast5_fp
  ```

We are 
For the actual nanopore fast5 signal data, 

### Quality Control


### Assembly
    
### Polishing

### Genome annotation

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/zhaoc1/nanoflow.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
