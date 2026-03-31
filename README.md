# 3D-OCT-to-HE-Translation
This repository contains the implementation of a deep learning-based framework for 3D virtual staining, specifically designed to translate label-free Full-Field Optical Coherence Tomography (FF-OCT) volumetric images into highly accurate Hematoxylin and Eosin (H&amp;E) histology images.

By leveraging advanced 3D spatial architectures (such as 3D U-Net and label-assisted SNRGAN) alongside a segmentation-guided approach for skin layers and nuclei, this framework ensures high morphological fidelity and structural consistency in the generated medical images.

This project is built to support both model training from scratch and direct inference (testing) using pre-trained networks.

# Key Features
End-to-End 3D Translation: A complete pipeline capable of handling high-resolution 3D volumetric data for medical image translation.

Segmentation-Guided Architecture: Utilizes specialized loss functions (e.g., Dice, Tversky) and auxiliary segmentation networks to refine the structural details of the virtual H&E staining.

Training & Inference Pipelines: The core logic is encapsulated within 3D_OCTtoH&E.ipynb, providing clear, step-by-step execution blocks for both training new models and generating predictions.

Out-of-the-Box Inference: All necessary pre-trained model weights and parameter files (.pth or .pkl) are securely stored in the Model/ directory, allowing researchers to apply the virtual staining to new FF-OCT data immediately without re-training.

# Repository Structure
3D_OCTtoH&E.ipynb: The main Jupyter Notebook containing the code for data loading, model architecture definitions, training loops, and inference execution.

Model/: This directory contains all the pre-trained network parameters (.pth or .pkl). The notebook is configured to load these weights directly for inference.

requirements.txt: Lists all Python dependencies required to reproduce the computational environment (compatible with local GPU setups and cloud platforms like TWCC).

# Usage
1. Environment Setup
Before running the code, please ensure your environment is set up correctly using the provided requirements file: pip install -r requirements.txt


2. Running Inference (Application)
To apply the virtual staining to your own FF-OCT data:
The script is pre-configured to automatically load the trained weights from the Model/ folder. Simply specify your input data path and execute the cells to generate the 3D H&E output.

3. Model Training
If you wish to train the networks from scratch or fine-tune them on a custom dataset:
Open 3D_OCTtoH&E.ipynb.
Navigate to the Training section.
Configure your hyper-parameters, batch sizes, and dataset directories.

4. The training blocks include the implementation of various loss functions and optimization steps. It is highly recommended to run the training pipeline on a robust GPU environment (e.g., NVIDIA Tesla V100) due to the computationally intensive nature of 3D spatial data.
