# Lignin Oligomer Molecular Graph Analysis

This repository contains a comprehensive Jupyter notebook for analyzing lignin oligomer molecular structures using network theory and graph analysis.

## Overview

The `Lignin_Oligomer_Analysis.ipynb` notebook performs detailed analysis on lignin oligomers from the `LigninStructs_3.json` dataset, including:

1. **Atom-level molecular graph visualization** using RDKit and NetworkX
2. **Network statistics calculation** (degree, clustering, connectivity metrics)
3. **Aggregated analysis** across all oligomers in the dataset
4. **Monomer-level network analysis** using bond counts as connection proxies

## Features

### 🔬 Atom-level Analysis
- Molecular structure visualization with chemical drawings
- Network graph representations with element-colored nodes
- Comprehensive statistics: degree distribution, clustering coefficients, graph density
- Connectivity analysis: diameter, path lengths, centrality measures
- Chemical composition analysis: C:O:H ratios, aromaticity quantification

### 🧬 Monomer-level Analysis
- Inter-monomer connectivity patterns for DP=3 oligomers
- Bond type frequency analysis (BB, BO4, B5 linkages)
- Network topology classification (linear vs. branched structures)
- Statistical comparison across different oligomer configurations

### 📊 Statistical Analysis
- Correlation analysis between network properties
- Aggregated statistics across the entire dataset
- Data export functionality for further analysis
- Comprehensive summary reports

## Requirements

### Dependencies
The notebook requires the following Python packages:

```bash
pip install pandas matplotlib networkx rdkit numpy jupyter
```

### System Requirements
- Python 3.8+
- Jupyter Notebook or JupyterLab
- ~2GB RAM for processing the dataset
- Graphics support for molecular visualizations

## Usage

### Quick Start

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd Lignin-Seb
   ```

2. **Install dependencies:**
   ```bash
   pip install pandas matplotlib networkx rdkit numpy jupyter
   ```

3. **Launch Jupyter:**
   ```bash
   jupyter notebook
   ```

4. **Open and run the notebook:**
   - Open `Lignin_Oligomer_Analysis.ipynb`
   - Run all cells or execute step by step

### Testing Functionality

Before running the full notebook, you can test that all dependencies are working:

```bash
python3 test_notebook_functionality.py
```

This script validates:
- ✅ Data loading from JSON
- ✅ SMILES parsing with RDKit
- ✅ NetworkX graph creation
- ✅ Statistical calculations
- ✅ Visualization capabilities

## Dataset

The analysis uses `LigninStructs_3.json` containing:
- **5 lignin oligomers** with degree of polymerization (DP) = 3
- **Monomer type:** sg (syringyl-guaiacyl)
- **SMILES strings** for molecular structure representation
- **Bond count data** for inter-monomer linkage analysis
- **Molecular weights** and structural properties

### Data Structure
```json
{
  "monoType": "sg",
  "dp": 3,
  "ligninchains": [
    {
      "lg_id": "lg_3_0",
      "smilestring": "OC=1C=CC(=CC1OC)C(O)C...",
      "molWeight": 576.0,
      "bndCnts": {"BB": 1, "BO4": 1}
    }
  ]
}
```

## Output Files

The notebook generates several CSV files with analysis results:

- `lignin_atom_level_statistics.csv` - Detailed atom-level network metrics
- `lignin_monomer_level_statistics.csv` - Monomer-level connectivity data
- `lignin_summary_statistics.csv` - Aggregated statistical summaries
- `lignin_correlation_matrix.csv` - Property correlation analysis

## Key Results

### Expected Findings

Based on the DP=3 dataset, the analysis typically reveals:

- **Average oligomer size:** ~81 atoms per structure
- **Network density:** Low (~0.026) due to tree-like molecular topology
- **Aromaticity:** ~36% of atoms in aromatic rings
- **Dominant linkages:** BO4 (β-O-4) and BB (β-β) bonds
- **Topology:** Predominantly linear structures (100% for DP=3)

### Visualizations Generated

1. **Chemical structure drawings** - Traditional molecular representations
2. **Network graphs** - Atom-level connectivity with element coloring
3. **Statistical plots** - Distribution analysis and correlations
4. **Monomer topology diagrams** - Inter-monomer connection patterns

## Notebook Structure

### Section Overview

1. **Setup and Imports** - Library loading and configuration
2. **Data Loading** - JSON parsing and dataset overview
3. **Molecular Processing** - SMILES to NetworkX conversion
4. **Atom-level Visualization** - Chemical and network drawings
5. **Network Statistics** - Comprehensive metric calculation
6. **Aggregated Analysis** - Cross-oligomer comparisons
7. **Monomer Networks** - Inter-monomer connectivity analysis
8. **Summary Report** - Key findings and insights
9. **Data Export** - Results saving and reproducibility notes

### Execution Time
- **Full notebook:** ~2-3 minutes
- **Individual sections:** 10-30 seconds each
- **Memory usage:** <1GB peak

## Customization

### Extending the Analysis

The notebook can be easily modified to:

- **Add new metrics:** Extend the `calculate_atom_network_stats()` function
- **Include more oligomers:** Update the JSON dataset
- **Change visualizations:** Modify matplotlib and NetworkX plotting code
- **Export different formats:** Add new output functions

### Parameter Modifications

Key parameters that can be adjusted:

```python
# Visualization settings
plt.rcParams['figure.figsize'] = (12, 8)  # Plot size
pos_seed = 42  # Graph layout seed

# Analysis parameters  
dp = 3  # Degree of polymerization
correlation_threshold = 0.5  # Correlation significance
```

## Troubleshooting

### Common Issues

1. **RDKit not found:**
   ```bash
   pip install rdkit
   # or
   conda install -c conda-forge rdkit
   ```

2. **Visualization errors:**
   ```python
   import matplotlib
   matplotlib.use('Agg')  # Use non-interactive backend
   ```

3. **Memory issues:**
   - Reduce figure sizes: `plt.rcParams['figure.figsize'] = (8, 6)`
   - Process fewer oligomers at once

4. **SMILES parsing failures:**
   - Check for valid SMILES strings in the dataset
   - Verify RDKit installation

### Getting Help

For issues or questions:
1. Check the test script output: `python3 test_notebook_functionality.py`
2. Verify all dependencies are installed correctly
3. Review the notebook error messages for specific guidance

## Citation

If you use this analysis in your research, please cite:

```
Lignin Oligomer Molecular Graph Analysis
Repository: In-Silico-RG/Lignin-Seb
Analysis Notebook: Lignin_Oligomer_Analysis.ipynb
```

## License

This project is available under the repository's license terms.

---

**Last Updated:** January 2025  
**Tested With:** Python 3.12, RDKit 2025.3.4, NetworkX 3.5, Pandas 2.3.1