# Network Analysis and Classification of ADHD using fMRIs
by Rajas Gupta and Vijay Sharma

## About this Project

Autism spectrum disorder (ASD) is characterized by qualitative impairment in social reciprocity, and by repetitive, restricted, and stereotyped behaviors/interests. Previously considered rare, ASD is now recognized to occur in more than 1% of children. Despite continuing research advances, there is still an urgent need for methods to diagnose ASD at earlier ages and more reliably.

In this project we examine the potential of diagnosing ASD by extracting, analysing, and classifying networks from functional magnetic resonance images (fMRIs). We extract functional networks using independent component analysis and time series analysis. We perform graph analysis using global and nodal measures on the networks to look for quantitative differences between the networks of ASD and TD subjects. We use a support vector machine to classify the networks and perform a grid search using stratified 5-fold cross validation to determine its accuracy.

We found that the transitivity and clustering measures for the average ASD graph were higher than that of the average TD graph, indicating that ASD brains tend to have stronger neural circuits with fewer connections between them. We also found that the Frontal Gyrus region which is involved with high-level cognitive function is more connected in the TD network than ASD, and the Postcentral Gyrus which processes sensory input is more connected in ASD subjects than TD. Finally, using classification we determined that there are non-trivial differences in the extracted functional networks for ASD and TD subjects. Due to our classifier not benefiting from regularization, we infer that there is potential for classifiers to achieve accuracy significantly above our value of 0.62 if a larger training set is used. We believe this shows that network extraction for classification has potential as a diagnostic tool for ASD.


## How to run this code

Download this repository and install the required python libraries from requirments.txt.

network_extraction.ipynb is the notebook that gets the fMRI data from ABIDE of 120 subjects of ASD and TD categories. WARNING: Do not run this file as it takes atleast 8 hours to run the entire notebook and takes up around 10GB of space. Extracted networks are stored as adjacency matrices in ./data/networks folder

network_analysis.ipynb reads in the mean ASD and TD networks created by network_extraction.ipynb and analyzes them using global measures (density, clustering, and transitivity) and nodal measures of centrality.

network_classification.ipynb reads subject networks and trains several classifiers using 5-fold cross validation and grid search to find optimal accuracy to diagnose ASD.

## Datasets

[ABIDE I Preprocessed](http://fcon_1000.projects.nitrc.org/indi/abide/abide_I.html)
[Harvard-Oxford Atlas](http://ftp.nmr.mgh.harvard.edu/pub/dist/freesurfer/tutorial_packages/centos6/fsl_507/doc/wiki/Atlases.html)

