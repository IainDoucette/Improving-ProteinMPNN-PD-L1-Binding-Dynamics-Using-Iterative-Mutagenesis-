## Protein Sequence Mutation Optimization
Welcome to the Protein Sequence Mutation Optimization project! 🎉 This project helps you design and optimize protein sequences by applying point mutations and evaluating their effects. Using machine learning models like ESM-2 and MPNN, it explores how mutations impact protein behavior and binding affinity, ultimately helping you design better proteins for your research or therapeutic applications.

Table of Contents
What is this project?
Requirements
How to Use
How it Works
Visualizing Results
Contributing
What is this project?
The goal of this project is to help you optimize a given protein sequence by:

Identifying potential mutations that could improve its properties (like binding affinity or stability).
Scoring those mutations using machine learning models to predict how they might perform.
Iterating the design process, progressively updating the sequence based on the best mutations.
What's inside the code?
LLR (Log Likelihood Ratio) Heatmaps: Calculate and visualize the impact of mutations on your sequence.
Best Mutation Selection: Automatically apply the top mutations and optimize your protein sequence.
MPNN Scoring: Use a neural network model to predict the overall score for each mutated sequence.
Requirements
Before you dive in, you'll need a few things installed:

Python 3.x (ideally Python 3.8 or later)
PyTorch: For running machine learning models.
Transformers: To use pre-trained models like ESM-2.
NumPy, Matplotlib, and Scikit-learn for data handling and visualization.
JAX (required for MPNN scoring).
You can install all the necessary libraries with:

bash
Copy code
pip install torch transformers numpy matplotlib scikit-learn jax
Additionally, you may need to install other specific libraries for protein scoring or visualization.

How to Use
Prepare your Protein Sequence: Start with your wild-type protein sequence (the unmutated version).
Run the Optimization: Execute the Python script to begin the mutation and optimization process. The script will:
Calculate LLR values for each position in the sequence.
Select the best mutations based on those LLR values.
Apply the mutations iteratively and generate new sequences.
See the Results: The final output includes:
A heatmap showing how each mutation affects the sequence.
The optimized protein sequence with the best mutations applied.
To run it, just execute:

bash
Copy code
python optimize_protein_sequence.py
This will generate outputs including:

A heatmap showing mutation effects (LLR values).
The final protein sequence after applying the best mutations.
How it Works
Step 1: Initial Sequence & Heatmap
You start with an initial protein sequence. The script calculates how each mutation at each position would affect the sequence by using a pre-trained model (like ESM-2). The results are displayed as heatmaps of LLR values, which tell you how favorable each mutation is.

Step 2: Apply the Best Mutations
The program picks the best mutations based on the highest LLR scores and applies them to the sequence, improving it progressively. The process repeats in multiple iterations, with the sequence evolving with each round of mutation.

Step 3: Scoring with MPNN
After each mutation, the program uses an MPNN model to predict the overall score for the newly mutated sequence. This helps evaluate how well the sequence will perform in terms of stability or binding affinity.

Step 4: Visualization
Throughout the process, you get visual feedback in the form of heatmaps. These maps show how each mutation changes the sequence at different positions, so you can easily track the optimization progress.

Visualizing Results
Once the mutations are applied, a heatmap will be generated using Matplotlib. This heatmap shows the LLR scores for all possible mutations across each position in your protein sequence.

For example:

High LLR values (in yellow or white) mean that the mutation at that position is favorable.
Low LLR values (in dark blue or purple) mean the mutation is less favorable.
Here’s a preview of how the heatmap will look:


Additionally, you'll see the final optimized protein sequence along with the MPNN scoring that gives you an idea of its overall performance.

Contributing
If you’d like to contribute or suggest improvements, feel free to:

Fork the repository
Open an issue for any bugs or feature requests
Submit a pull request with your changes
We’re always happy to have more collaborators!
