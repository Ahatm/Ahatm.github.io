PlantVillage Dataset
Hugging Face Paper

PlantVillage Dataset Sample

The PlantVillage Dataset is an open access repository of 54,306 images of healthy and diseased plant leaves, collected to advance research in automated plant disease diagnosis. It covers 14 crop species and 26 diseases, making it one of the largest publicly available datasets for computer vision in agriculture.

This dataset was introduced in the paper "Using Deep Learning for Image-Based Plant Disease Detection" by Mohanty et al. (2016). The goal of this work is to enable the development of smartphone-based disease diagnosis systems to help farmers worldwide safeguard their yields.

Recommended: Usage via Hugging Face
The easiest way to use this dataset is via the Hugging Face Hub.

Installation:

pip install datasets
Usage: It provides pre-defined 80/20 train/test splits that strictly respect the leaf grouping logic to prevent data leakage.

from datasets import load_dataset

# Load the dataset (default: color images)
dataset = load_dataset("mohanty/PlantVillage", "color")
For more details on configurations (grayscale, segmented) and advanced splitting, see the Hugging Face Model Card.

Repository Structure
The repository is organized as follows:

.
├── raw/                  # Raw image data
│   ├── color/            # Original RGB images
│   ├── grayscale/        # Grayscale versions
│   └── segmented/        # Segmented images
├── leaf_grouping/        # Metadata for leaf grouping
├── scripts/              # Data generation scripts
├── plant_village.py      # Hugging Face dataset loader
└── README.md
Usage
Requirement: This codebase was written for Python 2.7. Please ensure you have a Python 2 environment.

Download Dataset
With git installed:

git clone https://github.com/spMohanty/PlantVillage-Dataset
cd PlantVillage-Dataset
Dataset Upload (Maintenance)
To update the dataset on Hugging Face (e.g., after modifying metadata or adding images), use the provided script. This script handles zipping the data, uploading files, and updating the README.

Prerequisites:

Install huggingface_hub (pip install huggingface_hub).
Login via CLI: huggingface-cli login.
Run:

python3 scripts/upload_to_hf.py
Data Generation
The shell scripts in scripts/ utilize create_db.py to generate different versions of the dataset. Note: These scripts may contain hardcoded paths specific to the original cluster environment. They are provided for reference.

To run the Python tools directly (using Python 2):

python2 create_db.py --help
Citation
If you use this dataset, please consider citing:

@article{Mohanty_Hughes_Salathé_2016,
    title   = {Using deep learning for image-based plant disease detection},
    volume  = {7},
    DOI     = {10.3389/fpls.2016.01419},
    journal = {Frontiers in Plant Science},
    author  = {Mohanty, Sharada P. and Hughes, David P. and Salathé, Marcel},
    year    = {2016},
    month   = {Sep}
} 
Author
Sharada Mohanty sharada.mohanty@epfl.ch
Marcel Salathé Marcel.Salathe@epfl.ch
Digital Epidemiology Lab, EPFL
