The scripts here help with preparing the final inputs for used with PySEER for GWAS analysis.

First:

The filter_snp_alignment.py script takes the alignment and fasta file from the SNP calling step and does
a series of filtering actions:

 1. Get and drop columns with N
 2. Get and drop identical columns
 3. Get and drop multiallelic columns
 4. Get and drop singleton columns
 5. Remove allese with MAF < 0.05 (number can be changed in script)
 6. Remove uniquely segregating variants
 
Usage: python filter_snp_alignment.py alignment.fasta positions_list output.fasta output_positions_list

Second:

The write_multiple_sample_VCF_from_pipeline.py script takes the output.fasta output_positions_list from the first step
and writes a composite VCF file that is the proper input for PySEER.

Usage: python write_multiple_sample_VCF_from_pipeline.py output.fasta output_positions_list output_multiple_VCFs_file.vcf