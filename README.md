# Missense Pathogenicity Analysis

A comprehensive analysis of ClinVar missense variants using amino acid features and machine learning to predict pathogenicity.

## Overview

This project analyzes missense variants from ClinVar to understand the relationship between amino acid properties and pathogenicity. It includes:

- **Data Processing**: ClinVar variant filtering and feature extraction
- **Amino Acid Features**: Grantham scores, polarity, charge, volume, BLOSUM62
- **AlphaFold Integration**: pLDDT confidence scores from AlphaFold models
- **Machine Learning**: Random Forest classifier with feature importance analysis
- **Visualization**: Comprehensive plots and performance metrics

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

## Methodology

1. **Data Collection**: Download and filter ClinVar missense variants
2. **Feature Engineering**: Extract amino acid properties and structural features
3. **AlphaFold Integration**: Download PDB structures and extract pLDDT scores
4. **Machine Learning**: Train Random Forest classifier with balanced classes
5. **Evaluation**: Comprehensive performance metrics and feature importance

## Results

The analysis shows that:
- **Grantham distance** is the most important feature for pathogenicity prediction
- **Volume changes** and **charge changes** also contribute significantly
- **AlphaFold pLDDT scores** provide additional structural context
- The model successfully identifies high-risk missense variants, achieving **ROC AUC of ~0.75** on test data
- The model 

## Dependencies

- Python 3.7+
- pandas, numpy, scikit-learn
- matplotlib, seaborn
- requests, biopython
- jupyter notebook