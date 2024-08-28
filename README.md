# Dataset Description: Regression Challenge for Multiple Delaminations Detection

## Overview
This dataset is designed to support the development and evaluation of regression models for detecting and characterizing multiple delaminations in composite laminates. It is generated using Finite Element Method (FEM) simulations, with a focus on Structural Health Monitoring (_SHM_) applications.

## Inputs
The input data consists of simulated strain measurements collected from composite laminate plates with varying numbers of delaminations. The strains are measured along the _x_ and _y_ directions at different sensor locations on the plate.

- **Number of Sensors:** 36
- **Strain Data:** Strain values in the _x_-direction ($\epsilon_x$) and _y_-direction ($\epsilon_y$) for each sensor.
- **Total Input Features:** 72 (36 $\epsilon_x$ values + 36 $\epsilon_y$ values)

### Input File Structure
Each row in the input file represents a different simulation case with the following format:

- Columns 1-36: Strain values in the _x_-direction ($\epsilon_x$)
- Columns 37-72: Strain values in the _y_-direction ($\epsilon_y$)

## Outputs
The outputs represent the parameters defining the delaminations in the composite laminate. Each delamination is characterized by its location, size, and orientation.

### Output Variables:
1. **_x_:** _x_-coordinate of the delamination center.
2. **_y_:** _y_-coordinate of the delamination center.
3. **_a_:** Major semi-axis of the elliptical delamination.
4. **_b/a_:** Aspect ratio (minor/major axis ratio) of the elliptical delamination.
5. **$\theta$:** Orientation of the delamination ellipse relative to the _z_-axis.

### Output File Structure
Each row in the output file corresponds to the parameters for one or more delaminations in the same simulation case as the input file:

- **Single Delamination Case:**
  - Columns 1-5: [ $x_1$, $y_1$, $a_1$, $b/a_1$, $\theta_1$ ]
  
- **Two Delaminations Case:**
  - Columns 1-10: [ $x_1$, $y_1$, $a_1$, $b/a_1$, $\theta_1$, $x_2$, $y_2$, $a_2$, $b/a_2$, $\theta_2$ ]
  
- **Three Delaminations Case:**
  - Columns 1-15: [ $x_1$, $y_1$, $a_1$, $b/a_1$, $\theta_1$, $x_2$, $y_2$, $a_2$, $b/a_2$, $\theta_2$, $x_3$, $y_3$, $a_3$, $b/a_3$, $\theta_3$ ]



## File Naming Conventions
- **Input Files:** Named as `input_X_damage.txt`, where `X` represents the number of delaminations (1, 2, or 3).
- **Output Files:** Named as `output_X_damage.txt`, where `X` represents the corresponding number of delaminations in the input file.


## Data Generation Process
The dataset was generated using the ANSYS Parametric Design Language (_APDL_) in conjunction with FEM simulations. The parameters of each delamination (location, size, and orientation) were randomly varied within predefined limits to ensure diversity in the dataset.

## Applications
This dataset is ideal for testing and comparing regression models, including Machine Learning (_ML_) and Deep Learning (_DL_) algorithms, for the accurate detection and characterization of delaminations. It provides a challenging environment for developing advanced _SHM_ techniques.

## Citation
If you use this dataset in your research, please cite the corresponding publication:

- _Manuscript under revision._
