# Coherence Dataset

## Dataset Organization

You can find a directory for each dataset (**Wikipedia** or **Ted**).
Each directory contains a subdirectory for each language (**en**, **es**, **fr**, **it** and **pt**).

Inside the language directory there are two directories (positive configuration):
- **backwards**: contains data for the configurations where the target sentence is *before* the prompt;
- **forward**: contains data for the configurations where the target sentence if *after* the prompt.

This two directories contain 5 subdirectories indicating how the negative target are chosen (negative configuration):
- **pre_10**: the target sentence is the *10th sentence before* the first sentence of the prompt;
- **pre_5**: the target sentence is the *5th sentence before* the first sentence of the prompt;
- **5**: the target sentence is the *5th sentence after* the last sentence of the prompt;
- **10**: the target sentence is the *10th sentence after* the last sentence of the prompt;
- **out**: the target sentence is randomly chosen is *randomly chosen* from a document that is not the one containing the prompt.

## Dataset construction

All the diffierent configurations share the same prompts.
For what regards positive samples, they are always the same within the two positive configuration (forward or backwards). Across the two configuration, they share only the prompt, while the target sentence is the one following (forward) or preceding (backwards) the prompt.
For wath regards negative examples, they also share the prompt across all positive and negative configurations. They differ in the way the target sentence is chosen.

## Dataset dimension

Each configuration has **8000 training** samples and **800 test** samples, equally divided between positive and negative examples.
