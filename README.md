# Predicting Recrystallization in Laser Powder Techniques

## Abstract

Laser Powder Bed Fusion (LPBF) of metallic powders is a cutting-edge technique to manufacture 3D metallic parts with high flexibility compared to traditional methods. However, ensuring consistent repeatability remains a major challenge due to the lack of effective real-time quality monitoring.

This project focuses on detecting one specific phenomenon: **recrystallization** — the process where atoms or molecules arrange into a well-defined, rigid crystal lattice to minimize their energy state, often resulting in highly desirable mechanical properties.

Current recrystallization detection methods are complex and time-consuming. We propose an alternative approach using sound wave analysis: by recording audio during LPBF experiments and applying machine learning models to extracted acoustic features, we aim to detect whether recrystallization has occurred.

## Dataset and Setup

We collected sound recordings from multiple microphones during controlled experiments, where we know whether recrystallization occurred.

**Important:**  
- The total dataset exceeds 60 GB.
- **Downloading the dataset is NOT necessary** to run the provided Jupyter notebooks, as all outputs are already included.

If you still wish to access the raw data, it can be found here:  
🔗 [Dataset Link](https://drive.google.com/drive/folders/1PcH489NZ1Q1HGvnXvazfBNfYToG4CHyl?usp=sharing)

**Directory placement:** Download and place the dataset folders in the same directory as the code files.

### CSV File Naming Conventions
- `*deformed*` in filename: Recrystallization **occurred** during laser heat treatment.
- `*RX*` in filename (i.e., "previously recrystallized"): Recrystallization **did not occur** during treatment.

## Code Structure

The repository contains three main Jupyter notebooks:

- **`project.ipynb`**  
  Contains exploratory data analysis (EDA) templates and the YAMNet-based transfer learning implementation.

- **`svm.ipynb`**  
  Implementation of a Support Vector Machine (SVM) model for recrystallization detection.

- **`neural_net.ipynb`**  
  Implementation of a regular feed-forward neural network model.

> **Note:** Some code duplication exists between notebooks because each model was developed independently, using customized data preprocessing pipelines based on shared EDA functions. This approach was chosen to maximize solution diversity due to the absence of dedicated data science mentorship.

## Results

The main challenge was **not** model development but rather **effective feature extraction** from the acoustic signals.

- **SVM and regular neural network models**:  
  Achieved over **99% accuracy** with appropriate signal processing and feature extraction techniques.

- **YAMNet transfer learning model**:  
  Performed poorly. The pretrained feature extraction layers failed to meaningfully differentiate between our experimental sounds, likely due to being too generalized for our specific signals.

Overall, the SVM and neural network approaches demonstrated successful recrystallization detection. Once trained, the models run quickly enough to allow **real-time** implementation during experiments, rather than as post-processing.

## Notes on Code Duplication

Due to the exploratory nature of this project and limited available feedback, we initially collaborated on EDA before splitting to develop individual models. As a result, some data handling and preprocessing functions are duplicated across notebooks to allow flexible model-specific adjustments.
