## Summary
This project explores several Explainable AI (xAI) techniques applied to a binary classification problem: identifying Glioma types. Gliomas are the most common brain tumor types, and can be graded as LGGs (Lower-Grade Glioma) or GBMs (Glioblastoma Multiforme). It was developed for the course IF807 - Responsible AI.

Author: Carolina Berrafato

## Methodology

1. Five Machine Learning models were trained using scikit-learn: Decision Tree, Random Forest, Logistic Regression, k-Nearest Neighbours (kNN), and Support Vector Classifier (SVC).
2. As requested for the assignment, I explored some Decision Tree rules by calculating coverage and confidence levels for some nodes.
3. The best model based on its F1-Score was chosen (Logistic Regression), so the xAI methods could be applied.
 
    - *F1-Score was chosen as the main metric because in a real scenario, not only errors could lead to serious consequences, but also molecular tests are expensive. Thus, balancing precision and recall is crucial and prioritized over accuracy.*
    - *Even though Logistic Regression is already considered an interpretable model, it led to the best results, so all experiments were still made using it - except for the Global Surrogate. This last one was made for the Random Forest Model.*

4. Applied xAI techniques: Feature Importances, Surrogate Models (Global Surrogate, Local Surrogate -> LIME), Partial Dependence Plots (PDPs).

The notebook is organized into sections, and after each section, there is an interpretation of the results. Notebook's language is Portuguese. A brief summary of the general conclusions is presented below.

## Conclusions
- `IDH1` is the most important feature for the LR's decision-making. If there is a mutation in `IDH1` (`IDH1 > 0.5`), the glioma type tends to be LGG. Otherwise (`IDH1 <= 0.5`), the glioma tends to be classified as GBM.
- Other features can vary in contributing to the decision-making, but `IDH1` is still the most significant, impacting how much other variables contribute to the final classification. This can be observed in the PDPs.
- Patient's age at diagnosis, and mutations in IDH2 and NOTCH2 can significantly impact the model's decision for specific instances. 
