# royce-psdi-crystallm-training

Teaching materials for a hands-on introduction to neural networks and attention mechanisms, with an emphasis on building intuition from first principles before moving toward modern language-model concepts.

The current course materials are organised around two main practical themes:

- a from-scratch multilayer perceptron in NumPy, covering toy data generation, activation functions, loss functions, forward propagation, backpropagation, parameter updates, mini-batching, and training dynamics
- an introductory attention notebook, covering scaled dot-product attention, token embeddings, attention weights, and how attention leads naturally into transformer-style models

This repository is intended to hold a mixture of teaching assets:

- `notebooks/` for interactive practicals and worked examples
- `slides/` for lecture decks and presentation material
- `notes/` for written teaching notes and session plans
- `data/` for datasets and supporting files used in the practicals
- `scripts/` for helper utilities such as setup, preprocessing, or demo scripts

## Current materials

- [notebooks/mlp-from-scratch-numpy-teaching.ipynb](./notebooks/mlp-from-scratch-numpy-teaching.ipynb) introduces a teaching version of an MLP built entirely with NumPy, including student tasks
- [notebooks/mlp-from-scratch-numpy-teaching-solutions.ipynb](./notebooks/mlp-from-scratch-numpy-teaching-solutions.ipynb) provides the completed companion notebook
- [notebooks/attention.ipynb](./notebooks/attention.ipynb) introduces scaled dot-product attention with simple NumPy implementations and visualisations

As the course develops, the `notes/`, `slides/`, and `data/` directories can be expanded alongside the notebooks to provide a complete set of training materials.
