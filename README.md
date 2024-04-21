# Sequence Classification with Graph-Based Features

This Python project leverages the power of graph-based machine learning techniques to classify biological sequences. By converting sequences into k-mers, detecting overlaps, constructing an overlap graph, and employing Graph2Vec for embedding, the script enables effective classification with Support Vector Machines (SVM).

## Features

- **K-mer Generation**: Breaks down sequences into overlapping substrings of length k, capturing local sequence information.
- **Overlap Detection**: Identifies overlapping regions between k-mers to construct meaningful graph connections.
- **Graph Construction**: Builds an undirected graph where nodes represent k-mers and edges signify overlaps.
- **Graph Embedding**: Utilizes the Graph2Vec algorithm to convert the graph structure into a dense vector representation.
- **SVM Classification**: Employs SVM to classify sequences based on their graph embeddings.

## Prerequisites

Before you begin, ensure you have Python 3.8+ installed on your system. The project relies on several Python libraries listed below:

- NetworkX

- Matplotlib
- pandas
- scikit-learn
- KarateClub

## Installation

### Setup Python Environment

It's recommended to use a virtual environment for Python projects to manage dependencies effectively:

```bash
python -m venv venv
source venv/bin/activate  # Unix/MacOS
venv\Scripts\activate  # Windows
```

### Install Required Packages

Install all required packages using pip:

```bash
pip install networkx matplotlib pandas scikit-learn karateclub
```

## Usage

To use this project, follow the steps below:

1. **Prepare Your Data**: Ensure your data is in a text file where each line contains a sequence followed by its label, separated by a tab.

2. **Run the Script**: Use the script by specifying the input file and parameters for k-mer length and minimum overlap.

### Example

Here's how to run the script with example parameters:

```python
# Import the main function from the script
from your_script import main

# Specify the filename and parameters
filename = 'hum_med.txt'
k_values = [100, 200, 300]  # Example k-mer lengths
min_overlap_values = [50, 100, 150]  # Example minimum overlaps

# Execute the main function
results = main(filename, k_values, min_overlap_values)
print(results)
```

### Plotting and Graph Export

The script automatically generates visualizations of the overlap graphs and saves embeddings. Check the output files in your specified directory.

## Built With

- **NetworkX** - Graph creation and manipulation.
- **Matplotlib** - Visualization of data and graphs.
- **pandas** - Data manipulation and analysis.
- **scikit-learn** - Machine learning and data processing.
- **KarateClub** - Complex network embeddings including Graph2Vec.

## Contributing

Contributions to enhance the functionality or efficiency of this project are welcome. Please fork the repository and submit a pull request with your changes.
