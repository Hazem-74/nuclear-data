# Nuclear Data Analysis

This directory contains Jupyter notebooks for acquiring, processing, and analyzing nuclear data. The notebooks demonstrate scientific computing techniques using Python, focusing on the exploration and visualization of various nuclear properties.

## Files

### `Scraping Data.ipynb`

- **Purpose:** To programmatically acquire raw nuclear data from an online source and organize it into a structured format for further analysis.
- **Key Methods:**
    - Uses the `requests` library to download a `.txt` file containing nuclear data from a specified URL (`drhbctable.jcnp.org`).
    - Employs `pandas` to read an existing `Data.csv` file (presumably a processed version of the scraped data or a related dataset).
    - Iterates through unique proton numbers (Z) in the dataset to filter and save subsets of data into individual CSV files, creating a separate file for each isotopic chain (fixed Z).
    - Utilizes system commands (`zip`) to compress the generated directory of Z-specific data files into a single `.zip` archive.
- **Main Logic:** This notebook first downloads a comprehensive nuclear data table. It then takes a master `Data.csv` file, likely derived from such a table, and systematically organizes it by splitting the data into separate files based on the proton number (Z), making it easier to analyze specific isotopic chains. Finally, it archives these organized files for convenience.

### `Nuclear Data Analysis.ipynb`

- **Purpose:** To perform extensive exploratory data analysis (EDA) and visualization of nuclear properties derived from the `Data.csv` file. This notebook aims to uncover trends, relationships, and compare theoretical predictions with experimental observations.
- **Key Methods:**
    - Leverages `pandas` for data loading, cleaning (handling missing values, type conversion), and manipulation.
    - Utilizes `matplotlib.pyplot` and `seaborn` for creating a diverse range of static and statistical plots.
    - Generates scatter plots to compare experimental versus calculated values (e.g., binding energies, charge radii), visualize nuclear radii (neutron, proton, matter) against nucleon numbers, and illustrate nucleon deformations and Fermi levels.
    - Creates line plots to show trends of separation energies and Fermi levels as functions of neutron, proton, or mass numbers, and to depict S2n trends across isotopic chains.
    - Employs heatmaps to visualize the distribution of properties like binding energy and matter deformation across the nuclear chart (Z vs. N).
    - Computes and visualizes a correlation matrix of various nuclear parameters to identify strong relationships.
    - Includes a `seaborn.pairplot` for a broad overview of variable distributions and pairwise relationships.
- **Main Logic:** This notebook focuses on interpreting nuclear physics data. It starts by preparing the `Data.csv` for analysis. It then systematically visualizes key nuclear properties—such as binding energies, separation energies, radii, deformations, and Fermi levels—to identify patterns, shell closures, and structural changes. A significant part involves comparing theoretical model predictions (e.g., DRHBc) with available experimental data and exploring the interdependencies between different nuclear characteristics through correlation analysis.