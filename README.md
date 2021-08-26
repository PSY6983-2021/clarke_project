<a href="https://github.com/natasha-clarke">
   <img src="https://avatars.githubusercontent.com/u/57987005?v=4?s=100" width=$
   <br /><sub><b>Natasha Clarke</b></sub>
</a>

## Background

Since obtaining my MSc in Clinical Psychology in 2011, I have undergone clinical and research training in the fields of neurodegenerative diseases and mental health. I have a particular interest in disorders of memory and language, and the application of computational approaches to improve health outcomes. I was recently awarded my PhD from St George's University (London, UK), during which I used Natural Language Processing techniques to extract linguistic features from speech, and trained machine learning models to a) classify early Alzheimer's disease, and b) predict current and future cognitive performance. I am currently a Postdoctoral Fellow at the Badhwar MIND Lab, where my research is focused on using both structural and functional neuroimaging measures to find distinct subtypes of Alzheimer's disease.

For my brainhack project I wanted to learn to use functional connectivity analysis tools, github, and Compute Canada.

## Project definition

Haemodynamic changes in the brain, reflecting neuronal activity, can be imaged using blood-oxygen-level-dependent functional Magnetic Resonance Imaging (BOLD-fMRI) (Conklin et al., 2014). Fluctuations in this signal that correlate across spatially disparate brain regions reveal distributed networks that are functionally coupled. Associated with specific cognitive functions, networks are evident both whilst undertaking tasks and as spontaneous fluctuations whilst the brain is at rest (Yeo et al., 2011). Changes in resting state fMRI are evident in neurological diseases including Alzheimer's disease, and could be used as a biomarker to aid in dignosis and staging. Previously, machine learning has been used to automatically cluster individuals with Alzheimer's disease, Mild Cognitive Impairment, or ageing healthy, based on functional connectivity in different networks (Orban et al., 2017). These clusters represent subtypes of disease with distinct connectivity profiles. However, clustering based on the language network was not performed as part of this work, despite evidence that suggests that Alzheimer's disease can cause perterbations in language function (Clarke et al., 2020). Therefore, for my project I aimed to investigate the utility of clustering individuals with Alzheimer's disease and cognitively unimpaired persons using connectivity of the language network as input features.   

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

For my project I used Python and Jupyter notebooks to develop a resting state functional connectivity pipeline. The pipeline computes seed-based connectivity, calculating the correlation between a seed region and four regions of interest (ROIs). As part of this development I researched the language network, and based my notebook on a paper by Battistella et al. (2020), which reports seed regions and ROIs for sub-portions of the language network. I picked the 'semantic' sub-portion, as the semantic system is thought to be particularly vulnerable to Alzheimer's disease (Clarke et al., 2021). These calculations are then used to cluster data, utilising three different algorithms (Agglomerative with Ward clustering, Agglomerative with Average clustering and K Means clustering).



