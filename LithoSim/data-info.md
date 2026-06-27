# Dataset Information

<div>
    <img width="900" src="../assets/img/lithosim/data.png" class="center"> 
</div>

LithoSim benchmark is partitioned to evaluate simulation performance across in-distribution and out-of-distribution (OOD) scenarios. 

For each mask category (Metal, OPC-Metal, Via, OPC-Via), the corresponding data samples are stratified into training (0.7), validation (0.1), and testing (0.2) subsets. 
The validation set serves for hyperparameter tuning and early stopping, while the test set quantifies in-distribution predictive accuracy. 
Crucially, splits are performed independently per mask type to prevent cross-contamination between original (Metal, Via) and OPC-corrected (OPC-Metal, OPC-Via) layouts, mitigating biases in learning mask-correction synergies.

To assess generalization beyond training distributions, the OOD dataset, comprising M3/via layer clips and unconventional illumination (dipole, quasar), is reserved exclusively for testing. 
This separation ensures that OOD evaluation reflects real-world scenarios where models encounter unseen design rules, optical conditions, or process variation drifts.