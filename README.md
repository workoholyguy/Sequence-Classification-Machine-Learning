# Sequence Classification with Graph-Based Features (De-Bruijn Graphs, Overlap Graphs, Embedding, SVM )

This Python project leverages the power of graph-based machine-learning techniques to classify biological sequences. By converting sequences into k-mers, detecting overlaps, constructing an overlap graph, and employing Graph2Vec for embedding, the script enables effective classification with Support Vector Machines (SVM).

![overlap_graph_680](https://github.com/workoholyguy/Sequence-Classification-Machine-Learning/assets/95881196/676905fd-af14-4ff6-b7b9-4f482c6e6112)

![over_g_580](https://github.com/workoholyguy/Sequence-Classification-Machine-Learning/assets/95881196/ed4b06a7-8bac-4082-af22-d58f44e4192b)

![over_g_480_2](https://github.com/workoholyguy/Sequence-Classification-Machine-Learning/assets/95881196/7f53e4e4-8cce-4b14-ac30-5e2abc10d95b)

![h_o_gr_1K_250](https://github.com/workoholyguy/Sequence-Classification-Machine-Learning/assets/95881196/1f5323e0-5ca0-4704-b693-ea5d709237ed)

![h_o_gr_200_40](https://github.com/workoholyguy/Sequence-Classification-Machine-Learning/assets/95881196/361f2fde-3006-4af2-962a-26db3141f722)

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

## How to run

1. Download "olc_02.ipynb" and input_data into the same folder
2. Open olc_02.ipynb in your code editor.
3. Make sure you select correct file name "filename = 'input_data/hum_med_5.txt'" depending on which dataset you're willing to use.

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
