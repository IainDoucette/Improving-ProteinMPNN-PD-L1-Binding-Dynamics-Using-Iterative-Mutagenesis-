## Improving ProteinMPNN PD-L1 Binding Dynamics Using Iterative Mutagenesis

Welcome to the **Protein Sequence Mutation Optimization** project. This project aims to design and optimize protein sequences by applying point mutations and evaluating their effects. Using machine learning models like **ESM-2** and **MPNN**, it explores how mutations impact protein behavior and binding affinity, ultimately aims to design better proteins for research or therapeutic purposes.

## Table of Contents
- [What is this project?](#what-is-this-project)
- [Requirements](#requirements)
- [How it Works](#how-it-works)
- [Visualizing Results](#visualizing-results)
- [Credits](#credits)
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

bash
pip install torch transformers numpy matplotlib scikit-learn jax

## How it Works

The project follows a structured process to optimize a protein sequence by applying point mutations. Here's a breakdown of how it works:

### Step 1: **Initial Sequence & Heatmap Generation**
You start with an initial wild-type protein sequence. The script calculates the **Log Likelihood Ratio (LLR)** for each mutation at every position in the sequence using a pre-trained machine learning model, like **ESM-2**. The LLR values indicate how favorable each mutation is compared to the wild-type residue.

These LLR values are then used to generate a **heatmap** that visually represents the predicted impact of mutations on the sequence. The heatmap helps you identify which positions in the protein sequence are most likely to benefit from mutations.

### Step 2: **Selecting the Best Mutations**
Based on the generated heatmap, the script identifies the **best mutations** by selecting the ones with the highest LLR values (the most favorable mutations). These mutations are applied to the protein sequence, effectively changing its amino acid residues.

The program then iterates through this process, applying mutations to improve the protein sequence further.

### Step 3: **Applying the Mutations**
For each iteration, the script applies the selected mutations to the protein sequence. This is done by replacing the original residues with the mutated ones based on the mutation positions determined in Step 2. As the script iterates, the protein sequence is progressively optimized.

### Step 4: **MPNN Scoring for Optimization**
After each round of mutation, the updated protein sequence is evaluated using an **MPNN (Message Passing Neural Network)** model. The MPNN model predicts how well the new protein sequence will perform based on its structure, stability, or binding affinity.

The **MPNN score** gives a numerical value that represents the overall quality or fitness of the mutated sequence. This helps you assess whether the sequence has been improved.
![image](https://github.com/user-attachments/assets/48cbb9fa-bdb5-4ce1-a8f0-cf973d8e449a)

### Step 5: **Iterating the Process**
The program repeats this process multiple times (based on a predefined number of iterations). In each iteration:
1. It evaluates the current sequence for potential mutations.
2. It applies the best mutations to improve the sequence.
3. It re-scores the new sequence using the MPNN model.

This iterative process gradually enhances the protein sequence.

### Step 6: **Visualization of Results**
Throughout the optimization process, the script generates heatmaps that visualize the LLR values for mutations at each position in the sequence. These heatmaps show:
- **High LLR values** (typically in yellow or white) indicate mutations that are favorable and improve the protein’s properties.
- **Low LLR values** (typically in dark blue or purple) indicate mutations that are less favorable and might degrade the protein.

Finally, once the best mutations have been applied, the final optimized protein sequence and its associated **MPNN score** are outputted. This gives you a clear picture of the optimized sequence’s predicted performance.

In summary, the process helps you **design proteins** with higher potential for stability, binding, or other desired properties, based on scientific predictions and machine learning models.

## Visualizing Results

Throughout the optimization process, visualizations are used to help understand the effects of mutations on the protein sequence. The primary visualization methods used in this project are **heatmaps**.
These heatmaps allow us to see regions that are highly conserved and that cannot be easily mutated or that have very restricted mutations that are not deleterious. We also see the opposite, where there are residues or regions that can be easily mutated to almost any amino acid without detrimental effects. 

### Heatmaps 
Heatmaps are generated to visualize the **Log Likelihood Ratio (LLR)** scores for each mutation at every position in the protein sequence. These heatmaps allow you to quickly assess which mutations are most 

- **High LLR values** (usually in yellow) represent mutations that are favorable and improve the protein’s properties.
- **Low LLR values** (usually in dark blue ) represent mutations that are less favorable and could degrade the protein's properties.

#### Example Heatmap - Initial Heatmap of MPNN Generated Sequence

*Figure 1: Heatmap showing LLR scores of mutations in the protein sequence. High values indicate favorable mutations.*
![image](https://github.com/user-attachments/assets/da9a7a46-10a2-418e-a2d5-51e70c4ade16)


### Final Protein Sequence
The final optimized protein sequence is displayed after the iterative mutation process. This sequence is expected to have improved properties compared to the original.


## Credits
MPNN: https://github.com/sokrypton/ColabDesign/blob/main/af/examples/af_relax_design.ipynb

Heatmaps: https://huggingface.co/blog/AmelieSchreiber/protein-optimization-and-design

My PDB: 
https://www.rcsb.org/structure/5JDR

What is PD-L1: 
https://www.cancer.gov/publications/dictionaries/cancer-terms/def/pd-l1

https://medlineplus.gov/lab-tests/pdl1-immunotherapy-tests/#:~:text=Immunotherapy%20helps%20your%20own%20immune,healthy%20cells%20in%20your%20body.

Future Directions:
https://github.com/dauparas/LigandMPNN

https://github.com/flyark/AFM-LIS






