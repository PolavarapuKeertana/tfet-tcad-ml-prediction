This directory contains Python implementations of regression-based machine learning models used to construct surrogate predictors for the drain current (I<sub>DS</sub>)
of a Double-Gate n-type TFET device. The models learn device behavior directly from physics-consistent datasets generated using Silvaco ATLAS TCAD simulations.

Each script independently loads the compiled TFET dataset, performs train–test splitting, trains a regression model, and evaluates prediction accuracy using
standard performance metrics such as R² and mean squared error (MSE).

The implementations focus on model generalization, reproducibility, and clear comparison between different regression approaches, enabling fast TFET performance
prediction without repeated TCAD simulations.
