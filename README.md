# Protein Sequence Mutation Optimization

Welcome to the **Protein Sequence Mutation Optimization** project. This project aims to design and optimize protein sequences by applying point mutations and evaluating their effects. Using machine learning models like **ESM-2** and **MPNN**, it explores how mutations impact protein behavior and binding affinity, ultimately aims to design better proteins for research or therapeutic purposes.

## Table of Contents
- [What is this project?](#what-is-this-project)
- [Requirements](#requirements)
- [How to Use](#how-to-use)
- [How it Works](#how-it-works)
- [Visualizing Results](#visualizing-results)

## What is this project?

The goal of this project is to help you optimize a given protein sequence by:
- **Identifying potential mutations** that could improve its properties (like binding affinity or stability).
- **Scoring those mutations** using machine learning models to predict how they might perform.
- **Iterating the design process**, progressively updating the sequence based on the best mutations.

### What's inside the code?
1. **LLR (Log Likelihood Ratio) Heatmaps**: Calculate and visualize the impact of mutations on your sequence.
2. **Best Mutation Selection**: Automatically apply the top mutations and optimize your protein sequence.
3. **MPNN Scoring**: Use a neural network model to predict the overall score for each mutated sequence.

## Requirements
The code requires the following libraries to run

- **Python 3.x** (ideally Python 3.8 or later)
- **PyTorch**: For running machine learning models.
- **Transformers**: To use pre-trained models like **ESM-2**.
- **NumPy**, **Matplotlib**, and **Scikit-learn** for data handling and visualization.
- **JAX** (required for MPNN scoring).

You can install all the necessary libraries with:

```bash
pip install torch transformers numpy matplotlib scikit-learn jax

