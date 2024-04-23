# Sequence Classification with Graph-Based Features (De-Bruijn Graphs, Overlap Graphs, Embedding, SVM )

This Python project leverages the power of graph-based machine-learning techniques to classify biological sequences. By converting sequences into k-mers, detecting overlaps, constructing an overlap graph, and employing Graph2Vec for embedding, the script enables effective classification with Support Vector Machines (SVM).

![overlap_graph_680](https://github.com/workoholyguy/Sequence-Classification-Machine-Learning/assets/95881196/676905fd-af14-4ff6-b7b9-4f482c6e6112)

![over_g_580](https://github.com/workoholyguy/Sequence-Classification-Machine-Learning/assets/95881196/ed4b06a7-8bac-4082-af22-d58f44e4192b)

![over_g_480_2](https://github.com/workoholyguy/Sequence-Classification-Machine-Learning/assets/95881196/7f53e4e4-8cce-4b14-ac30-5e2abc10d95b)

![h_o_gr_1K_250](https://github.com/workoholyguy/Sequence-Classification-Machine-Learning/assets/95881196/1f5323e0-5ca0-4704-b693-ea5d709237ed)

![h_o_gr_200_40](https://github.com/workoholyguy/Sequence-Classification-Machine-Learning/assets/95881196/361f2fde-3006-4af2-962a-26db3141f722)

## Features

- **K-mer Chopping:** Converts DNA sequences into k-mers of specified lengths to capture essential sequence features.
- **Overlap Detection:** Identifies overlaps between k-mers to find possible connections, which helps in building the graph.
- **Graph Construction:** Constructs an undirected graph where nodes represent k-mers and edges represent overlaps, with weights corresponding to the overlap size.
- **Graph Visualization:** Generates visual representations of the constructed graph to aid in visual analysis.
- **Node Embedding:** Utilizes Node2Vec to generate vector embeddings for each node in the graph, enhancing the feature space for machine learning.
- **Classification:** Employs an SVM classifier to categorize nodes based on their embeddings, useful for predicting biological features or relationships.

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

## How to run

1. Download "olc_02_02-Improved_code.ipynb" and input_data into the same folder
2. Open olc_02_02-Improved_code.ipynb in your code editor.
3. Make sure you select correct file name "filename = 'input_data/hum_med_500.txt'" depending on which dataset you're willing to use.

### Setup

Prepare your input data in a tab-separated values (TSV) file with two columns: `sequence` and `class`. Each line should represent a DNA sequence and its corresponding class or category.

### Configuration

Edit the `filename`, `k_values`, and `min_overlap_values` variables in the script:

- `filename`: Path to your input TSV file.
- `k_values`: List of k-mer sizes to analyze (e.g., `[150, 250, 350]`).
- `min_overlap_values`: List of minimum overlap lengths to consider for constructing the graph (e.g., `[50, 100, 149]`).

### Outputs

The script outputs:

- PNG files for each constructed graph visualized.
- GraphML files for each graph to allow further computational analysis.
- Terminal output includes accuracy and classification reports which summarize the performance of the SVM classifier.

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
