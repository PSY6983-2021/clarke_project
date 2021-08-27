<a href="https://github.com/natasha-clarke">
   <img src="https://avatars.githubusercontent.com/u/57987005?v=4?s=100" width=$
   <br /><sub><b>Natasha Clarke</b></sub>
</a>

## Background

Since obtaining my MSc in Clinical Psychology in 2011, I have undergone clinical and research training in the fields of neurodegenerative diseases and mental health. I have a particular interest in disorders of memory and language, and the application of computational approaches to improve health outcomes. I was recently awarded my PhD from St George's University (London, UK), during which I used Natural Language Processing techniques to extract linguistic features from speech, and trained machine learning models to a) classify early Alzheimer's disease, and b) predict current and future cognitive performance. I am currently a Postdoctoral Fellow at the Badhwar MIND Lab, where my research is focused on using both structural and functional neuroimaging measures to find distinct subtypes of Alzheimer's disease.

For my brainhack project I wanted to learn to use functional connectivity analysis tools, github, and Compute Canada.

## Project definition

Haemodynamic changes in the brain, reflecting neuronal activity, can be imaged using blood-oxygen-level-dependent functional Magnetic Resonance Imaging (BOLD-fMRI) (Conklin et al., 2014). Fluctuations in this signal that correlate across spatially disparate brain regions reveal distributed networks that are functionally coupled. Associated with specific cognitive functions, networks are evident both whilst undertaking tasks and as spontaneous fluctuations whilst the brain is at rest (Yeo et al., 2011). Changes in resting state fMRI are evident in neurological diseases including Alzheimer's disease, and could be used as a biomarker to aid in diagnosis and staging. Previously, machine learning has been used to automatically cluster individuals with Alzheimer's disease, Mild Cognitive Impairment, or ageing healthy, based on functional connectivity in different networks (Orban et al., 2017). These clusters represent subtypes of disease with distinct connectivity profiles. However, clustering based on the language network was not performed as part of this work, despite evidence that suggests that Alzheimer's disease can cause perturbations in language function (Clarke et al., 2020). Therefore, for my project I aimed to investigate the utility of clustering individuals with Alzheimer's disease and cognitively unimpaired persons using connectivity of the language network as input features.   

### Research goals/ outline

1. Cluster cognitively unimpaired controls and patients with Alzheimer's disease, based on resting state functional connectivity of the language network
2. Compare different clustering algorithms, aiming to minimise the intra-cluster variation
3. Test associations between clusters and cognitive performance

### Tools

- Jupyter notebooks and Python, particularly the nilearn and scikit-learn libraries
- High Performance Computing using Compute Canada
- Github to host a repository of notebooks

### Deliverables

At the end of this project, I will have:

1. A github repository containing notebooks with pipelines for clustering, statistical analyses and visualisation of results
2. Used Compute Canada to run scripts on larger dataset

### Data

I will use resting state functional connectivity data from the Alzheimer's Disease Neuroimaging Initiative (ADNI) dataset, which has been preprocessed using NIAK (Bellec et al. 2011, https://niak.simexp-lab.org/)

## Results

For my project I used Python and Jupyter notebooks to develop a resting state functional connectivity pipeline. The pipeline computes seed-based connectivity, calculating the correlation between a seed region and four regions of interest (ROIs). As part of this development I researched the language network, and based my notebook on a paper by Battistella et al. (2020), which reports seed regions and ROIs for sub-portions of the language network. I picked the 'semantic' sub-portion, as the semantic system is thought to be particularly vulnerable to Alzheimer's disease (Clarke et al., 2021). However the notebook can be easily edited to calculate seed-based connectivity for (m)any ROIs. Connectivity results are then used to cluster data, utilising three different algorithms (Agglomerative with Ward clustering, Agglomerative with Average clustering and K Means clustering). I also discovered and used the PyMatch library, which uses propensity scores to match patients and controls on a number of different variables - awesome!

Deliverable 1: The notebooks can be found in this current repository (I am also working on a separate repository on my github). `functional_connectivity_clustering.ipynb` computes the seed-based connectivity and builds clustering algorithms. It outputs a dataframe of the seed-ROIs correlations and a numpy array of the same for later analysis, and three pickled clustering models. You will beed a bunch of functional connectivity files in nifty format (.nii), and corresponding confound files. Also, two .txt files: one listing the func files, and one listing the confound files.
`clustering_visualization.ipynb` is used to load the models, compute summary statistics/scores and visualize results. It includes functions to calculate a clustering algorithm's accuracy, sensitivity and specificity, when true class labels are known. The Silhouette coefficient/score, a measure of 'goodness' of the clustering technique that ranges from -1 to 1, can be calculated, and clustering techniques compared and visualized. Finally, correlations can be performed between cluster scoring and variables such as cognition or age.

Deliverable 2: I used Compute Canada, wahoo! Functional connectivity and clustering were developed locally using a matched ADNI dataset, and then run on HPC with a larger dataset of 54 participants.

### Research results

Based on 54 participants in ADNI (14 AD, 40 cognitively unimpaired controls), the clustering failed to find clusters of language network functional connectivity profiles that were associated with global cognition. Some explanations for the findings may be that the dataset used was small for clustering, and contained few patients; connectivity was calculated for only a sub-portion of the language network with four ROIs; MMSE score was used as a measure of global cognition, which, although contains a few questions relating to language function, does not effectively probe semantic language (the sub-section of the language network being evaluated). Thus, I will try on a larger dataset, with more ROIs. I will also investigate a different technique to assess cluster goodness, which results in a continuous measure of similarity between data points in a cluster and the prototypical cluster subject.

*Figures will be added here*


## References

Battistella, G., Borghesani, V., Henry, M., Shwe, W., Lauricella, M., Miller, Z., ... & Gorno-Tempini, M. L. (2020). Task-free functional language networks: reproducibility and clinical application. Journal of Neuroscience, 40(6), 1311-1320.

Bellec, P., Carbonnell, F., Perlbarg, V., Lepage, C., Lyttelton, O., Fonov, V., ... & Evans, A. (2011). A neuroimaging analyses kit for Matlab and Octave. In Human Brain Mapping HBM 2011 17th Annual Meeting of the Organization on Human Brain Mapping, Quebec City, Canada, June 26-30, 2011 (pp. 1-5). Organization on Human Brain Mapping.

Conklin, C. J., Faro, S. H., & Mohamed, F. B. (2014). Technical considerations for functional magnetic resonance imaging analysis. Neuroimaging Clinics of North America, 24(4), 695-704.

Clarke, N., Foltz, P., & Garrard, P. (2020). How to do things with (thousands of) words: Computational approaches to discourse analysis in Alzheimer's disease. Cortex, 129, 446-463.

Clarke, N., Barrick, T. R., & Garrard, P. (2021). A Comparison of Connected Speech Tasks for Detecting Early Alzheimer's Disease and Mild Cognitive Impairment Using Natural Language Processing and Machine Learning. Frontiers in Computer Science, 3, 634360.

Orban, P., Tam, A., Urchs, S., Savard, M., Madjar, C., Badhwar, A., ... & Alzheimer’s Disease Neuroimaging Initiative. (2017). Subtypes of functional brain connectivity as early markers of neurodegeneration in Alzheimer’s disease. BioRxiv, 195164.

Thomas Yeo, B. T., Krienen, F. M., Sepulcre, J., Sabuncu, M. R., Lashkari, D., Hollinshead, M., ... & Buckner, R. L. (2011). The organization of the human cerebral cortex estimated by intrinsic functional connectivity. Journal of neurophysiology, 106(3), 1125-1165.