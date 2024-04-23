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

1. Download "olc_02_02.ipynb" and input_data into the same folder
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

As the developer who improved the sequence classification code using overlap graphs, I made several key enhancements and modifications to optimize performance and functionality. Here’s a detailed comparison and the rationale behind these changes:

### **Key Differences and Improvements**

1. **Logging Integration**:
   - **Original Version**: Did not include any logging, which can limit debuggability and traceability of the code execution.
   - **Improved Version**: I integrated Python’s `logging` module, which allows tracking the execution process and debugging more effectively. This is especially useful in production environments or during further development to understand flow and errors.

2. **Function Enhancements**:
   - **Original Version**: Functions are straightforward but lack efficiency in handling large datasets or minimizing repetitive computations.
   - **Improved Version**: I optimized the `chop_into_kmers` function using a list comprehension for better performance. Additionally, I enhanced overlap detection logic to exit early once a sufficient overlap is found, reducing unnecessary comparisons.

3. **Graph Construction**:
   - **Original Version**: The graph construction was somewhat basic, mapping k-mers to unique indices but not ensuring efficient memory usage or scalability.
   - **Improved Version**: In constructing the overlap graph, I retained the efficient mapping but streamlined the addition of edges and nodes to ensure it scales better with larger datasets. I also included explicit logging at this stage to notify when a graph has insufficient data, enhancing the robustness of the dataset handling.

4. **Graph Analysis and Exporting**:
   - **Original Version**: Lacked detailed analysis or exporting functionality which could limit the utility in real-world applications.
   - **Improved Version**: I added a function, `evaluate_graph`, to compute and log various graph metrics like density and clustering coefficient, providing insights into the graph structure. This is critical for understanding the quality of the graph in terms of connectivity and clustering properties.

5. **Node2Vec Integration**:
   - **Original Version**: Utilized Graph2Vec without considerations for empty graphs or alignment issues between node embeddings and labels.
   - **Improved Version**: I switched to Node2Vec for more customizable node embedding and handled cases where the graph might be empty. This flexibility allows for better tuning according to specific characteristics of the data. I ensured that the node labels align correctly with their embeddings, which is crucial for accurate classification.

6. **Error Handling and Data Alignment**:
   - **Original Version**: Did not focus on error handling or data misalignment, which could lead to failures or incorrect results during classification.
   - **Improved Version**: I implemented checks to ensure there are at least two classes before proceeding with SVM training, and aligned labels directly with embeddings to prevent misclassification due to misaligned data.

7. **Scalable and Organized File Management**:
   - **Original Version**: Simplistic handling of output files.
   - **Improved Version**: I introduced organized directory structures for saving graphs and results based on k-mer and overlap values, which simplifies managing outputs from multiple runs or datasets.

### **Conclusion**

The improvements I implemented are designed to enhance the scalability, robustness, and utility of the sequence classification using overlap graphs. By integrating better logging, optimizing functions, adding graph evaluations, and ensuring error handling and data alignment, the script is now more suitable for larger datasets and provides more insights into the generated models and graphs.