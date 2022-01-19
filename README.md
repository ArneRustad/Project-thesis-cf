# Model-Based Counterfacual Synthesizer Using Tabular GAN and a Comparison to Algorithmic Based Counterfactuals


This is a Github repository for the code associated with Arne Rustad's project thesis. Below we describe briefly what each code file's purpose is and give the abstract for the written project thesis titled *"Model-Based Counterfacual Synthesizer Using Tabular GAN and a Comparison to Algorithmic Based Counterfactuals"*


## Code file explanations

1. **Imports.ipynb**: This jupyter notebook file contains all the imports required by the different scripts in this repository. They are created as a separate file that can be loaded to avoid repeating the process for each script and to make it an easy process to update package requirements.
2. **explore_and_clean_adult_dataset.R**: This R file contains the code performing very simple exploratory analysis of the Adult dataset in addition to preprocessing of the Adult dataset. Lastly, it also prints the latex code required for the summary tables of the Adult datasets used in the project report.
3. **tabGAN.ipynb**: This jupyter notebook file contains the Python class for the methods tabGAN, tabGAN-qt, tabGAN-qtr and tabGAN-cf referenced in the paper.
4. **utils.ipynb**: Jupyter notebook file containing all the help functions used by later Python scripts.
5. **plot_parteto_frontier_example.R**: R code file for generating the Pareto frontier figure in the project thesis paper.
6. **tabGAN_plot_model_for_adult_dataset.ipynb**: Jupyter notebook file for creating svg drawings of the generator and critic architecture for the tabGAN method fitted to the Adult dataset. Both svg images were included in the paper.
7. **tabGAN_evaluate_on_toy_datasets.ipynb**: Jupyter notebook file where the performance of the tabGAN data synthesizer is evaluated on two simulated (toy) datasets.
8. **TabFairGAN_nofair.ipynb**: The modified code for the tabFairGAN method (and thus the tabFairGAN-mod method described in this paper). The original code script was fetched from (https://github.com/amirarsalan90/TabFairGAN).
9. **TGAN_generate_synthetic_datasets.ipynb**: Jupyter notebook file for generating the synthetic datasets used in the analyses in the jupyter notebook files *tabGAN_compare_on_adult_dataset.ipynb* and *tabGAN_compare_prediction_on_synthetic_adult_dataset.ipynb*. The reason the synthetic datasets created using TGAN need to be created in a different file is that TGAN requires Tensorflow version 1, while tabGAN, tabGAN-qt and tabGAN-qtr is implemented for Tensorflow version 2. Thus we had to create separate Anaconda environments. The link to the Github repository for TGAN is (https://github.com/sdv-dev/TGAN)
10. **tabFairGAN_generating_synthetic_datasets**: Jupyter notebook file for generating the synthetic datasets used in the analyses in the jupyter notebook files *tabGAN_compare_on_adult_dataset.ipynb* and *tabGAN_compare_prediction_on_synthetic_adult_dataset.ipynb*.
11. **tabGAN_compare_on_adult_dataset.ipynb**: Jupyter notebook file for performing comparison of the methods tabGAN, tabGAN-qt, tabGAN-qtr, TGAN, CTGAN, tabFairGAN and tabFairGAN-mod with respect to recreation of marginal and pairwise joint column distributions.
12. **tabGAN_compare_prediction_on_synthetic_adult_dataset.ipynb**: Jupyter notebook file for performing comparison of the methods tabGAN, tabGAN-qt, tabGAN-qtr, TGAN, CTGAN, tabFairGAN and tabFairGAN-mod with respect to machine learning efficacy (test AUC and accuracy on the original Adult test dataset for XGBoost models trained on synthetic train datasets generated by the different data synthesizer methods).
13. **hyperparameter_tuning_exgboost_adult.ipynb**: Jupyter notebook file for performing hyperparameter tuning of XGBoost on the Adult dataset. NOT USED IN THE THESIS.
14. **create_counterfactuals_with_moc.ipynb**: Jupyter notebook file for creating counterfactual explanations for the analysis performed in *compare_counterfactuals_on_adult_dataset.ipynb*.
15. **compare_counterfactuals_on_adult_dataset.ipynb** Jupyter notebook file for comparing counterfactuals generated by the model-based counterfactual method tabGAN-cf developed in this thesis and the algorithmic-based counterfactual method MOC. The counterfactual methods were compared informally on a simulated dataset and the Adult dataset.


## Project thesis abstract

> Counterfactual explanations are an emerging method for explaining predictions from black box models by utilizing "what-if" scenarios. In this thesis, we define a model-based counterfactual synthesizer, tabGAN-cf, utilizing generative adversarial networks (GAN) and a post-processing step consisting of Monte Carlo sampling in combination with filtering. During the creation of tabGAN-cf, we also invent three different GAN based data synthesizers: tabGAN, tabGAN-qt and tabGAN-qtr. The two latter methods rely on quantile transformation and for the case of tabGAN-qtr, a novel stochastic version of quantile transformation that we introduce in this thesis. We compare the datasynthesizers against three state-of-the-art methods (TGAN, CTGAN and tabFairGAN). The results suggest that tabGAN, tabGAN-qt and tabGAN-qtr perform on par with or better than state-of-the-art methods for the experiments in this thesis. The implementation of the newly defined data synthesizers also run substantially faster than TGAN and CTGAN. We informally compare the newly created model-based counterfactual method, tabGAN-cf, to a well-known algorithmic-based method, MOC. The informal evaluation reveals a substantial gap between the two methods in favor of tabGAN-cf with respect to time efficiency and the desired prediction outcome, whilst MOC appears superior with respect to generating sparse counterfactual explanations.

