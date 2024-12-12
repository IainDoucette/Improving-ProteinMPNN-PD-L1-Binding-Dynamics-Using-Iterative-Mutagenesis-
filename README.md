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
