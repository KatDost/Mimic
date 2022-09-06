# MIMIC

Machine Learning can help overcome human biases in decision making by focussing on purely logical conclusions based on the training data. If the training data is biased, however, that bias will be transferred to the model and remains undetected as the performance is validated on a test set drawn from the same biased distribution.

Existing strategies for selection bias identification and mitigation generally rely on some sort of knowledge of the bias or the ground-truth. An exception is the [Imitate](https://github.com/KatDost/Imitate) algorithm that assumes no knowledge but comes with a strong limitation: It can only model datasets with one normally distributed cluster per class. 

In our PAKDD paper (Citation below), we introduce a novel algorithm, MIMIC, which uses Imitate as a building block but relaxes this limitation. By allowing mixtures of multivariate Gaussians, our technique is able to model multi-cluster datasets and provide solutions for a substantially wider set of problems.

Experiments confirm that MIMIC not only identifies potential biases in multi-cluster datasets which can be corrected early on but also improves classifier performance. The results are given in our PAKDD paper, however, we offer supplementary material and results [here](Mimic_Supplementary.pdf).

# Citation
If you want to use this implementation or cite MIMIC in your publication, please cite the following PAKDD paper:
```
Katharina Dost, Hamish Duncanson, Ioannis Ziogas, Patricia Riddle, and Jörg Wicker.
"Divide and Imitate: Multi-Cluster Identification and Mitigation of Selection Bias."
In: Advances in Knowledge Discovery and Data Mining - 26th Pacific-Asia Conference, PAKDD 2022. 
Lecture Notes in Computer Science, vol. 13281, pp. 149-160. Springer, Cham (2022).
```

Bibtex:
```
@inproceedings{Dost2022,
title = {Divide and Imitate: Multi-Cluster Identification and Mitigation of Selection Bias},
author = {Katharina Dost and Hamish Duncanson and Ioannis Ziogas and Pat Riddle and J\"{o}rg Wicker},
year = {2022},
booktitle = {Advances in Knowledge Discovery and Data Mining - 26th Pacific-Asia
               Conference, {PAKDD} 2022},
series    = {Lecture Notes in Computer Science},
volume    = {13281},
pages     = {149--160},
publisher = {Springer},
address   = {Cham},
doi       = {10.1007/978-3-031-05936-0\_12},
}
```

# How to use MIMIC
The supplementary material contains all the materials used to produce the outputs in the submitted paper together with our implementation of the MIMIC method. All implementation files are Jupyter Notebooks and require Python.

The implementation is structured as follows:
- [Mimic.ipynb](Mimic.ipynb): MIMIC algorithm
- [Exp_NoBias.ipynb](Exp_NoBias.ipynb): Experiment: MIMIC's behavior when no bias is present
- [Exp_Number_of_Bins.ipynb](Exp_Number_of_Bins.ipynb): Experiment: Which information criterion is best suited to select the number of bins in a histogram?
- [Exp_PredictionAcc_Synth.ipynb](Exp_PredictionAcc_Synth.ipynb): Experiments on synthetic data
- [Exp_PredictionAcc_RealData.ipynb](Exp_PredictionAcc_RealData.ipynb): Experiments on real data
- [Plots.ipynb](Plots.ipynb): Script generating all plots presented in the paper

Additional files containing our results are provided here:
- [Results](Results/): All raw results obtained by running the scripts provided above
- [Plots](Plots/): Plots generated from the raw results
