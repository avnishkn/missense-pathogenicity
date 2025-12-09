# Missense Pathogenicity Analysis

## Overview

This project analyzes ClinVar missense variants (single-nucleotide changes causing amino acid substitutions) to predict their pathogenicity. Combines traditional biochemical features (Grantham, charge, polarity, volume) with modern structural data (AlphaFold confidence scores) to build a machine learning classifier that can distinguish pathogenic from benign mutations.

## Data Sources

ClinVar public archive of missense variants and their clinical significance; AlphaFold protein structures via UniProt gene-to-protein mapping.

## Features Analyzed

- **Grantham Distance**: Chemical similarity between amino acids
- **Volume Difference**: Molecular volume changes
- **Charge Change**: Electrostatic property changes  
- **Polarity Change**: Hydrophobicity changes
- **BLOSUM62 Score**: Evolutionary substitution likelihood
- **pLDDT Score**: AlphaFold confidence at mutation site

## Project Structure

```
├── missense_pathogenicity.ipynb    # Main analysis notebook
├── aa_features/                   # Amino acid property data
│   ├── grantham_matrix.csv
│   ├── aa_3to1_mapping.csv
│   ├── aa_polarity.csv
│   ├── aa_charge.csv
│   └── aa_volume.csv
└── README.md
```

## Analysis

1. Download and filter ClinVar missense variants
2. Extract amino acid features and AlphaFold pLDDT scores
3. Train Random Forest classifier (balanced classes)
4. Evaluate performance and feature importance

## Results

- **Grantham distance** is the most important predictor of pathogenicity, with some significant contributions from **volume changes** and **charge changes**
- Model successfully identifies high-risk missense variants with initial ROC AUC ~0.75 on initial test data

## Dependencies

- Python 3.7+
- pandas, numpy, scikit-learn
- matplotlib, seaborn
- requests, biopython
- jupyter notebook

## References

- ClinVar: https://www.ncbi.nlm.nih.gov/clinvar/
- AlphaFold Database: https://alphafold.ebi.ac.uk/
- UniProt: https://www.uniprot.org/
- Landrum et al., Nucleic Acids Research, 2018: https://academic.oup.com/nar/article/46/D1/D1062/4617959