# 🧬 VCF to TSV Converter using `bcftools`

A lightweight utility to convert VCF (Variant Call Format) files into TSV (tab-separated values) format using `bcftools`. This tool is ideal for users who wish to quickly extract key variant information for further analysis in R, Python, or spreadsheet applications.

---

## 📚 Table of Contents

- [Overview](#overview)
- [Installation](#installation)
- [Usage](#usage)
- [Field Explanation](#field-explanation)
- [Example Output](#example-output)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

This project provides a simple command that uses `bcftools` to parse VCF files and output essential variant data in a tab-delimited format. It helps create quick summaries or feed data into other analysis pipelines.

---

## 📦 Installation

Ensure you have [Conda](https://docs.conda.io/en/latest/) installed before proceeding. Use the following command to install `bcftools` via the Bioconda channel:

```bash
conda install -c bioconda bcftools
This command will install bcftools along with any necessary dependencies on your system.

## 🚀 Usage
To convert a VCF file into TSV format, simply run:

bcftools query -f '%CHROM\t%POS\t%ID\t%REF\t%ALT\t%QUAL\t%FILTER\t[%GT\t]\n' input.vcf > output.tsv

----
## Explanation
The format string provided to bcftools query uses placeholders to represent VCF fields:

Placeholder	Description
%CHROM	Chromosome name
%POS	Genomic position of the variant
%ID	Variant identifier
%REF	Reference allele
%ALT	Alternate allele(s)
%QUAL	Quality score
%FILTER	Filter status (e.g., PASS)
%GT	Genotype(s) for each sample (if present)
Feel free to modify the format string to include additional fields as required for your analyses.

##📁 Example Output
The output TSV file will contain rows of variant data formatted as follows:
CHROM	POS	    ID	    REF	ALT	    QUAL	FILTER	GT
chr1	123456	.	    A	G	    99	    PASS	0/1
chr1	789101	rs123	T	C	    80	    PASS	1/1
## 🤝 Contributing
Contributions are welcome! If you have suggestions, bug fixes, or additional features, please open an issue or submit a pull request. For major changes, please discuss them via issue first to ensure that the changes align with the project's objectives.


