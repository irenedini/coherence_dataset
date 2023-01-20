# Coherence Dataset

## Dataset Organization

In this repository you can find the dataset for the paper **Coherent or Not? Stressing a Neural Language Model for Discourse
Coherence in Multiple Languages**. The dataset is organised in two directories: **Wikipedia** and **Ted**.
Each directory contains a subdirectory for each language (**en**, **es**, **fr**, **it** and **pt**).

Each language directory contains two directories:
- **backwards**: contains data for the classification experiments in which the target sentence is *before* the prompt;
- **forward**: contains data for the classification experiments in which the target sentence if *after* the prompt.

This two directories contain 5 subdirectories indicating how the negative targets are chosen:
- **pre_10**: the target sentence is the *10th sentence before* the first sentence of the prompt;
- **pre_5**: the target sentence is the *5th sentence before* the first sentence of the prompt;
- **5**: the target sentence is the *5th sentence after* the last sentence of the prompt;
- **10**: the target sentence is the *10th sentence after* the last sentence of the prompt;
- **out**: the target sentence is *randomly chosen* from a document that is not the one containing the prompt.

## Dataset dimension

Each configuration has **8000 training** samples and **800 test** samples, equally divided between positive and negative examples.

## Data format

Each file is a .tsv file containing the following fields:
1) Sample id
2) prompt: 3 consecutive sentences divided by carriage returns (\n)
3) target: target sentence
4) label: 1 if the target is contiguous to the prompt (according to the configuration), 0 if not.
