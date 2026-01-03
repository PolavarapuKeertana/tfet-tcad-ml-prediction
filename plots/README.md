__Model Prediction Plots and Analysis__

This directory contains visualization results comparing __TCAD-simulated drain current (I<sub>DS</sub>)__ and __machine learning–predicted I<sub>DS</sub>__ under different biasing and parameter-variation scenarios for the Double-Gate n-type TFET.

All plots were generated using __OriginPro 2025b__ with logarithmic current scaling to accurately capture subthreshold and ON-state tunneling behavior.


__1. Training Dataset Performance (Gate Voltage Sweep)__

__Scenario__
• Gate–Source Voltage (V<sub>GS</sub>): 0–1.5 V (step = 0.005 V)  
• Drain–Source Voltage (V<sub>DS</sub>): 0.5 V  
• Gate Work Function (φ<sub>gate</sub>): 4.5 eV  
• Gate Length (L<sub>G</sub>): fixed (training configuration)

__Description__
These plots compare __actual TCAD I<sub>DS</sub>–V<sub>GS</sub> characteristics__ with __ML-predicted I<sub>DS</sub>__ for samples drawn from the training dataset.

__Observations__
• All models closely track the TCAD curve across subthreshold and ON regions  
• Ensemble models (Random Forest, Gradient Boosting, LightGBM) show improved smoothness  
• XGBoost exhibits the best overlap with TCAD data across the full V<sub>GS</sub> range  


__2. Drain–Source Voltage Variation (V<sub>DS</sub> Vary)__

__Scenario__
• Gate–Source Voltage (V<sub>GS</sub>): 0–1.5 V  
• Gate Work Function (φ<sub>gate</sub>): 4.5 eV  
• Drain–Source Voltage (V<sub>DS</sub>): 0.75 V  

__Purpose__
To evaluate __model generalization__ when predicting device behavior under unseen drain bias conditions.

__Observations__
• ML models successfully extrapolate to intermediate V<sub>DS</sub> values  
• XGBoost and LightGBM maintain excellent agreement with TCAD data  
• Minor deviations appear only in deep subthreshold, indicating strong robustness  


__3. Gate Work Function Variation (φ<sub>gate</sub> Vary)__

__Scenario__
• Gate–Source Voltage (V<sub>GS</sub>): 0–1.5 V  
• Drain–Source Voltage (V<sub>DS</sub>): fixed  
• Gate Work Function (φ<sub>gate</sub>): varied around training range  

__Purpose__
To assess sensitivity of ML models to __electrostatic control changes__.

__Observations__
• ML predictions correctly capture threshold voltage shifts  
• Tunneling onset behavior remains well modeled  
• Ensemble methods outperform single-tree models in stability  


__4. Gate Voltage Sweep (V<sub>GS</sub> Vary)__

__Scenario__
• Gate–Source Voltage (V<sub>GS</sub>): swept  
• Other parameters held constant  

__Purpose__
To verify ML accuracy across both __subthreshold swing__ and __strong ON-state regimes__.

__Observations__
• Excellent agreement across several decades of I<sub>DS</sub>  
• Log-scale plots confirm correct learning of tunneling-dominated transport  
• No artificial smoothing or non-physical artifacts observed  


__5. Training vs Testing Performance (TD: Train–Test Split)__

__Dataset Split__
• 70% of data used for training  
• 30% of data used for testing (unseen samples)

__Description__
These plots compare __training and testing predictions__ to evaluate overfitting and generalization.

__Observations__
• Training and test curves overlap closely  
• No noticeable overfitting observed  
• XGBoost demonstrates strong generalization across bias conditions  


__Summary__

The plots collectively demonstrate that:
• ML surrogate models achieve __TCAD-level accuracy__  
• Ensemble models provide superior robustness  
• The framework generalizes well beyond training conditions  
• Device physics trends are preserved across all models  

These visualizations validate the suitability of the surrogate framework for __fast TFET design-space exploration__.
