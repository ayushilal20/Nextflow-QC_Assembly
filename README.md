# Nextflow Read Cleaning and Assembly Pipeline

This Nextflow pipeline performs read cleaning using Trimmomatic and assembly using Skesa.

## Requirements

- [Nextflow](https://www.nextflow.io/) - Install Nextflow on your system.
- [Trimmomatic](http://www.usadellab.org/cms/?page=trimmomatic) - Install Trimmomatic.
- [Skesa](https://github.com/ncbi/SKESA) - Install Skesa.
- Create conda environment with the required softwares

```bash
conda create -n wf -y
```
-Go into the 'wf' environment and install a bunch of utilities from the bioconda channel
```bash
conda activate wf
conda install -c bioconda -c conda-forge entrez-direct sra-tools fastqc trimmomatic skesa pigz -y
```

## Input Requirements

- Paired-end fastq files (`r1` and `r2`) for read cleaning.

## Pipeline Steps

1. **Trimming Reads with Trimmomatic:**
   - Trimmomatic is used to remove adapters and low-quality bases from the input reads.

2. **Assembly with Skesa:**
   - Skesa is used to perform de novo assembly of the trimmed reads.

## Usage
Run the pipeline:

    ```bash
    nextflow run tsk.nf --r1 /path/to/your/input/r1.fastq.gz --r2 /path/to/your/input/r2.fastq.gz 
    
    ```

    - Replace `/path/to/your/input/r1.fastq.gz` and `/path/to/your/input/r2.fastq.gz` with the actual paths to your input files.

## Additional Notes

- Customize the Trimmomatic and Skesa parameters in the `tsk.nf` script based on your specific requirements.
