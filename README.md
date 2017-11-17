<<<<<<< HEAD
# Combine_Pipelines
Combine_Pipelines
=======
# KnowEnG's General Clustering Pipeline 
This is the Knowledge Engine for Genomics (KnowEnG), an NIH BD2K Center of Excellence, General Clustering Pipeline.

This pipeline **clusters** a spreadsheet's columns, with various methods:

| **Options**                                      | **Method**                                   | **Parameters** |
| ------------------------------------------------ | ---------------------------------------------| -------------- |
| K-means                                          | K Means                                      | kmeans         |
| hierarchical clustering                          | hierarchical clustering                      | hclust         |
| Linked hierarchical clustering                   | hierarchical clustering constraint           | link_hclust    |
| Bootstrapped hierarchical clustering             | consensus hierarchical clustering            | cc_ hclust     |
| Bootstrapped K-means                             | consensus K Means                            | cc_kmeans      |
| Bootstrapped Linked hierarchical clustering      | consensus linked hierarchical clustering     | cc_link_hclust |     
=======
# KnowEnG's Gene Signature Pipeline 
This is the Knowledge Engine for Genomics (KnowEnG), an NIH BD2K Center of Excellence, Signature Analysis Pipeline.

This pipeline performs network-based **signature analysis** on the columns of a given spreadsheet, where spreadsheet's columns correspond to sample-labels and rows correspond to gene-labels.  The signature is based on correlating gene expression data (network enriched) against known gene signature data.

There are four similarity "signature"  methods that one can choose from:

- similarity        (traditional method) 
- net_similarity    (with network enrichment)
- cc_similarity     (with bootstraps)
- cc_net_similarity (with bootstraps and network enrichment)


and two correlation measures:
- spearman 
- cosine 

>>>>>>> Signature_Analysis_Pipeline/master

* * * 
## How to run this pipeline with Our data
* * * 
<<<<<<< HEAD
### 1. Clone the General_Clustering_Pipeline Repo
```
 git clone https://github.com/KnowEnG-Research/General_Clustering_Pipeline.git
```
 
### 2. Install the following, for Linux
```
 apt-get install -y python3-pip libfreetype6-dev libxft-dev libblas-dev liblapack-dev libatlas-base-dev gfortran
 pip3 install pyyaml knpackage scipy==0.19.1 numpy==1.11.1 pandas==0.18.1 matplotlib==1.4.2 scikit-learn==0.17.1 
```

### 3. Change directory to General_Clustering_Pipeline

```
cd General_Clustering_Pipeline
=======
### 1. Clone the Gene_Signature_Pipeline Repo
```
 git clone https://github.com/KnowEnG-Research/Gene_Signature_Pipeline.git
```
 
### 2. Install the following (Ubuntu or Linux)
  ```
 pip3 install pyyaml
 pip3 install knpackage
 pip3 install scipy==0.18.0
 pip3 install numpy==1.11.1
 pip3 install pandas==0.18.1
 pip3 install matplotlib==1.4.2
 pip3 install scikit-learn==0.17.1
 
 apt-get install -y python3-pip
 apt-get install -y libfreetype6-dev libxft-dev
 apt-get install -y libblas-dev liblapack-dev libatlas-base-dev gfortran
```

### 3. Change directory to Gene_Signature_Pipeline

```
cd Gene_Signature_Pipeline
>>>>>>> Signature_Analysis_Pipeline/master
```

### 4. Change directory to test

```
cd test
```
 
### 5. Create a local directory "run_dir" and place all the run files in it
```
make env_setup
```

<<<<<<< HEAD
### 6. Use one of the following "make" commands to select and run a clustering option:


| **Command**                     | **Option**                                 | 
|:------------------------------- |:-------------------------------------------| 
| make run_kmeans_binary          | Clustering with k-means                    |
| make run_kmeans_continuous      |                                            |
| make run_hclust_binary          | Hierarchical Clustering                    |
| make run_hclust_continuous      |                                            |
| make run_link_hclust_binary     | Hierarchical linkage Clustering            |
| make run_link_hclust_continuous |                                            |
| make run_cc_kmeans_binary       | Consensus Clustering with k-means          |
| make run_cc_kmeans_continuous   |                                            |
| make run_cc_hclust_binary       | Consensus Hierarchical Clustering          |
| make run_cc_hclust_continuous   |                                            |
| make run_cc_link_hclust_binary  | Consensus Hierarchical linkage Clustering  |
=======
### 6. Use one of the following "make" commands to select and run a similarity  option:


| **Command**              | **Option**                                              | 
|:-------------------      |:------------------------------------------------------- | 
| make run_spearman        | spearman similarity                                     |
| make run_net_spearman    | spearman similarity with network enrichment             |
| make run_cc_spearman     | spearman similarity with bootstraps                     |
| make run_cc_net_spearman | spearman similarity with bootstraps & network enrichment|
>>>>>>> Signature_Analysis_Pipeline/master

 
* * * 
## How to run this pipeline with Your data
* * * 

<<<<<<< HEAD
__***Follow steps 1-5 above then do the following:***__
=======
__***Follow steps 1-3 above then do the following:***__
>>>>>>> Signature_Analysis_Pipeline/master

### * Create your run directory

 ```
<<<<<<< HEAD
 mkdir run_dir
 ```

### * Change directory to the run directory

 ```
 cd run_dir
=======
 mkdir run_directory
 ```

### * Change directory to the run_directory

 ```
 cd run_directory
>>>>>>> Signature_Analysis_Pipeline/master
 ```

### * Create your results directory

 ```
<<<<<<< HEAD
 mkdir results
=======
 mkdir results_directory
>>>>>>> Signature_Analysis_Pipeline/master
 ```
 
### * Create run_paramters file  (YAML Format)
 ``` 
<<<<<<< HEAD
 Look for examples of run_parameters in the General_Clustering_Pipeline/data/run_files zTEMPLATE_cc_hclust.yml
=======
 Look for examples of run_parameters in the Gene_Signature_Pipeline/data/run_files zTEMPLATE_cc_net_spearman.yml
>>>>>>> Signature_Analysis_Pipeline/master
 ```
### * Modify run_paramters file  (YAML Format)
Change processing_method to one of: serial, parallel depending on your machine.
```
processing_method: serial
```

set the data file targets to the files you want to run, and the parameters as appropriate for your data.


<<<<<<< HEAD
### * Run the General Clustering Pipeline:
=======
### * Run the Gene Signature Pipeline:
>>>>>>> Signature_Analysis_Pipeline/master

  * Update PYTHONPATH enviroment variable
   ``` 
   export PYTHONPATH='../src':$PYTHONPATH    
   ```
   
  * Run
   ```
<<<<<<< HEAD
  python3 ../src/general_clustering.py -run_directory ./run_dir -run_file zTEMPLATE_cc_net_nmf.yml
=======
  python3 ../src/samples_signature.py -run_directory ./run_dir -run_file zTEMPLATE_cc_net_spearman.yml
>>>>>>> Signature_Analysis_Pipeline/master
   ```

* * * 
## Description of "run_parameters" file
* * * 

<<<<<<< HEAD
| **Key**                    | **Value**                    | **Comments**                                   |
| -------------------------  | ---------------------------- | ---------------------------------------------- |
| method                     |  **kmeans**,**hclust**,**link_hclust**,**cc_kmeans**, **cc_hclust**, **cc_link_hclust**| Choose clustering method                       |
| affinity_metric            | **euclidean**, **manhattan**, **jaccard** | Choose clustering affinity                     |
| linkage_criterion          | **ward**, **complete**, **average** | Choose clustering affinity              |
| spreadsheet_name_full_path | directory+spreadsheet_name      |  Path and file name of user supplied gene sets |
| results_directory          | directory                       | Directory to save the output files             |
| tmp_directory              | ./run_dir/tmp                   | Directory to save the temporary files          |
| number_of_clusters         | 3                               | Estimated number of clusters                   |
| number_of_bootstraps       | 4                               | Number of bootstraps for cc_kmeans, cc_hclust and cc_link_hclust|
| rows_sampling_fraction     | 0.8                             | Select 80% of spreadsheet rows                 |
| cols_sampling_fraction     | 0.8                             | Select 80% of spreadsheet columns              |
| top_number_of_rows         | 10                              | Top number of features to analyze              | 
| processing_method          | serial or parallel or distribute| Choose processing method                    |
| parallelism                | number of cores                 | Set number of cores for speed or memory|
| threshold                  | 10                              | Threshold to define categorical data and continuous data in evaluation toolbox| 
| nearest_neighbors          | 10                              | Number of Nearest Neighbors in cc_link_hclust method |

spreadsheet_name = EXPR_GSE_METABRIC_lymphN_binary.tsv.gz</br>
=======
| **Key**                   | **Value**                                           | **Comments** |
| ------------------------- | --------------------------------------------------- | ------------ |
| method                    | **similarity**, **cc_similarity**, **net_similarity** or **cc_net_similarity**  | Choose similarity  method |
| similarity_measure        | **spearman**, **cos**                               | Choose correlation  measure |
| gg_network_name_full_path | directory+gg_network_name                           | Path and file name of the 4 col network file |
| spreadsheet_name_full_path| directory+spreadsheet_name                          | Path and file name of user supplied gene sets |
| signature_name_full_path  | directory+signature_data_name                       | Path and file name of user supplied signature data |
| results_directory         | directory                                           | Directory to save the output files |
| tmp_directory             | directory                                           | Directory to save the intermediate files |
| rwr_max_iterations        | 100                                                 | Maximum number of iterations without convergence in random walk with restart |
| rwr_convergence_tolerence | 1.0e-8                                              | Frobenius norm tolerence of spreadsheet vector in random walk|
| rwr_restart_probability   | 0.7                                                 | alpha in `V_(n+1) = alpha * N * Vn + (1-alpha) * Vo` |
| rows_sampling_fraction    | 0.8                                                 | Select 80% of spreadsheet rows|
| number_of_bootstraps      | 4                                                   | Number of random samplings |
| processing_method         | serial or parallel or distribute                    | Choose processing method |

gg_network_name = STRING_experimental_gene_gene.edge</br>
spreadsheet_name = ProGENI_rwr20_STExp_GDSC_500.rname.gxc.tsv</br>
signature_data_name = 
>>>>>>> Signature_Analysis_Pipeline/master

* * * 
## Description of Output files saved in results directory
* * * 

<<<<<<< HEAD
* Output files of all  methods save row by col heatmap variances per row with name **row_variance_{method}_{timestamp}_viz.tsv**.</br>

 |  |**variance**|
 | :--------------------: |:--------------------:|
 | **row 1**              |float                 |
 |...                     |...                   |
 | **row m**              | float                |

* Output files of all the methods save row by col heatmap with name **row_by_col_heatmp_{method}_{timestamp}_viz.tsv**.</br>

 |  |**col 1**|...|**col n**|
 | :--------------------: |:--------------------:|:--------------------:|:--------------------:|
 | **row 1**              |float                 |...                   |float                 |
 |...                     |...                   |...                   |...                   |  
 | **row m**              |float                 |...                   |float                 |

 
* Output files of all  methods save col to cluster map with name **col_labeled_by_cluster_{method}_{timestamp}_viz.tsv**.</br>

 |    |**cluster**|
 | :--------------------: |:--------------------:|
 | **col 1**              |int                   |
 |...                     |...                   |
 | **col n**              |int                   |
 
* Output files of all  methods save row scores by cluster with name **row_averages_by_cluster_{method}_{timestamp}_viz.tsv**.</br>

 |  |**cluster 1**|...|**cluster k**|
 | :--------------------: |:--------------------:|:--------------------:|:--------------------:|
 | **row 1**              |float                 |...                   |float                 |
 |...                     |...                   |...                   |...                   |
 | **row m**              |float                 |...                   |float                 |
 
* Output files of all  methods save spreadsheet with top ranked rows per column with name **top_row_by_cluster_{method}_{timestamp}_download.tsv**.</br>

 |  |**cluster 1**|...|**cluster k**|
 | :--------------------: |:--------------------:|:--------------------:|:--------------------:|
 | **row 1**              |1/0                   |...                   |1/0                   |
 |...                     |...                   |...                   |...                   |
 | **row m**              |1/0                   |...                   |1/0                   |
  
* All  methods save **silhouette number of clusters** and **corresponding silhouette score** with name silhouette_average\_{method}\_{timestamp}\_viz.tsv.</br>
 ```
 File Example: 
 silhouette number of clusters = 3, corresponding silhouette score = 1
 ```
=======
* Output files of all four methods save samples by signature similarity "correlation" with name **similarity_matrix_{method}_{measure}_{timestamp}_viz.tsv**.</br>

 |                        |**signature 1**          |...                   |**signature m**       |
 | :--------------------: |:-----------------------:|:--------------------:|:--------------------:|
 | **sample 1**           |float                    |...                   |float                 |
 |...                     |...                      |...                   |...                   |
 | **sample n**           |float                    |...                   |float                 |
 
>>>>>>> Signature_Analysis_Pipeline/master
