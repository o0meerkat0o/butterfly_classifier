# butterfly_classifier

An image classifier that identifies the life stage of a monarch butterfly (**egg, larva, pupa, or adult**) from a photo, built for research at Cornell's Entomological Data Science Lab.

## Overview

The core of this project is `monarch_life_stage_classifier.ipynb`, a notebook that:

- Trains a 4-class image classifier (egg / larva / pupa / adult) on monarch butterfly photos sourced from **iNaturalist**
- Uses **Grounding DINO** to auto-crop images down to the relevant subject before classification, reducing background noise
- Fine-tunes **EfficientNetB0 / EfficientNetB1** as the classification backbone

## Notes

- An earlier version of the pipeline had a data-leakage bug that was silently inflating validation accuracy (e.g. near-duplicate or same-individual images ending up in both train and validation splits) — this has since been diagnosed and fixed.
- `test` is a placeholder file, not part of the pipeline.

## Getting started

1. Open `monarch_life_stage_classifier.ipynb` in Jupyter or Google Colab.
2. Install dependencies referenced in the notebook (TensorFlow/Keras for EfficientNet, plus a Grounding DINO implementation for auto-cropping).
3. Point the data-loading cells at your own iNaturalist export (or the dataset the notebook expects).
4. Run the notebook top to bottom to reproduce preprocessing, training, and evaluation.

## Status

Research project — expect the notebook format rather than a packaged library. Training data, exact hyperparameters, and evaluation results are documented inline in the notebook.
