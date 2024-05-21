# ML-Project-to-Predict-Antimicrobial-Peptides
This project demonstrates the development of a machine-learning model for predicting the antimicrobial activity of antimicrobial peptides (AMPs). It provides a comprehensive approach, guiding researchers through the entire bioinformatics workflow.


# Step 1
Download peptide feature data that already available in literature ( it is a zip file , we need to unzip it)
https://github.com/raghavagps/Pfeature/raw/master/PyLib/Pfeature.zip

This  will enable the computation of amino acid properties. This capability is essential for the subsequent quantification of molecular properties in peptides.

Before proceeding, let's briefly discuss peptides. Peptides are short chains of amino acids linked together. These chains can vary in size, ranging from dipeptides (containing just two amino acids) to larger structures with upwards of 50 amino acids.
# Step 2: Download the data set
https://raw.githubusercontent.com/dataprofessor/AMP/main/train_po.fasta
https://raw.githubusercontent.com/dataprofessor/AMP/main/train_ne.fasta


# Install CD-HIT and remove redundancy 

CD-HIT is a valuable tool for reducing redundancy in peptide sequence datasets. It efficiently identifies and removes highly similar peptides, resulting in a non-redundant or unique subset of sequences suitable for subsequent model building. This process ensures that the model is trained on the most informative and representative set of peptides, potentially improving its accuracy and generalizability.

# Calculate features using the Pfeature library
Pfeature library contains diffrent peptide features. like Amino acid composition, Dipeptide composition, etc. 
you can refer all features here https://www.google.com/url?q=https%3A%2F%2Fwebs.iiitd.edu.in%2Fraghava%2Fpfeature%2FPfeature_Manual.pdf



# Feature Engineering:

The feature_calculator function takes positive and negative datasets as input, along with the feature type (e.g., amino acid composition).
It calculates features for both datasets and combines them with class labels (positive/negative) into a single dataframe.

#Machine Learning Model Building:

The data is split into training and testing sets using an 80/20 ratio and stratified sampling to maintain class balance.
A lazy classifier approach is used, potentially involving multiple models to be evaluated later.
Matthew's correlation coefficient is chosen as a custom metric for model performance evaluation due to its ability to handle class imbalance.
Model performance is evaluated on both training and testing sets, including metrics like accuracy, Matthews correlation coefficient, confusion matrix, classification report, ROC curve (AUC), and feature importance plots.
