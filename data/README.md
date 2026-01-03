This directory contains datasets generated from Silvaco ATLAS TCAD simulations of the Double-Gate n-type TFET device. Raw simulation outputs were obtained in `.dat`
format and subsequently compiled into a structured Excel dataset for efficient data handling and machine learning workflows.

The compiled dataset is used for training, validation, and testing of machine learning surrogate models to predict TFET drain current (I<sub>DS</sub>) as a
function of device parameters and biasing conditions.

A representative sample `.dat` file is provided to illustrate the original TCAD output format. The Excel dataset consolidates multiple simulation sweeps into a
single, analysis-ready file to enable reproducibility and efficient model training.
