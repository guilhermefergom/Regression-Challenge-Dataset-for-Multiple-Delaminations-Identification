# Dataset Description: Regression Challenge for Multiple Delaminations Detection

## Overview
This dataset is designed to support the development and evaluation of regression models for detecting and characterizing multiple delaminations in composite laminates. It is generated using Finite Element Method (FEM) simulations, with a focus on Structural Health Monitoring (_SHM_) applications.

## ⚠️ Important: File Naming Convention
**Please note that the file naming convention in this dataset is counter-intuitive relative to standard Machine Learning terminology.**

* **Features (Model Inputs):** Are contained in the files named `output_X_damage.txt`.
* **Targets (Model Outputs):** Are contained in the files named `input_X_damage.txt`.

Please refer to the detailed descriptions below to ensure correct data loading.

---

## Features (Strain Data)
**Source File:** `output_X_damage.txt` (where `X` is 1, 2, or 3)

The features consist of simulated strain measurements collected from composite laminate plates.

-   **Number of Sensors:** 36
-   **Data Type:** Strain values measured at specific sensor locations.
-   **Total Input Features:** 36 columns

### Data Structure
Each row represents a different simulation case.
-   **Columns 1-36:** Strain values corresponding to the 36 sensors.

---

## Targets (Delamination Parameters)
**Source File:** `input_X_damage.txt` (where `X` is 1, 2, or 3)

The targets represent the geometric parameters defining the delaminations.

### Output Variables Order
The columns appear in the following order for each delamination:
1.  **$x$:** $x$-coordinate of the delamination center.
2.  **$y$:** $y$-coordinate of the delamination center.
3.  **$a$:** Major semi-axis of the elliptical delamination.
4.  **$\theta$:** Orientation of the delamination ellipse relative to the $z$-axis (in radians).
5.  **$b/a$:** Aspect ratio (minor/major axis ratio).

### Data Structure
Each row corresponds to the parameters for the delaminations in the corresponding row of the feature file.

**Single Delamination Case (`input_1_damage.txt`):**
- Columns 1-5: $[ x_1, y_1, a_1, \theta_1, b/a_1 ]$

**Two Delaminations Case (`input_2_damage.txt`):**
- Columns 1-10: $[ x_1, y_1, a_1, \theta_1, b/a_1, x_2, y_2, a_2, \theta_2, b/a_2 ]$

**Three Delaminations Case (`input_3_damage.txt`):**
- Columns 1-15: $[ x_1, y_1, a_1, \theta_1, b/a_1, x_2, y_2, a_2, \theta_2, b/a_2, x_3, y_3, a_3, \theta_3, b/a_3 ]$

---

## Data Generation Process
The dataset was generated using the ANSYS Parametric Design Language (_APDL_) in conjunction with FEM simulations. The parameters of each delamination (location, size, and orientation) were randomly varied within predefined limits to ensure diversity in the dataset.

## Applications
This dataset is ideal for testing and comparing regression models, including Machine Learning (_ML_) and Deep Learning (_DL_) algorithms, for the accurate detection and characterization of delaminations. It provides a challenging environment for developing advanced _SHM_ techniques.

## Citation
If you use this dataset in your research, please cite the corresponding publication:

**Gomes, G.F., Takano, V.D.** "Strain-based identification of multiple damages in plate-like structures using artificial intelligence and metaheuristic optimization." *Machine Learning for Computational Science and Engineering*, 2:5 (2026). https://doi.org/10.1007/s44379-025-00052-w
