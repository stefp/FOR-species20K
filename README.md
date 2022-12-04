
![3DForEcoTech-logo-description](https://user-images.githubusercontent.com/5663984/174446150-32e31872-2003-4af9-95d4-a1abfca0b744.png)

# Sensor-agnostic tree species classification using proximal laser scanning (TLS, MLS, ULS) and CNNs
Repository for the work related to the tree species classification using proximally sensed laser scanning data (TLS, MLS, ULS). This work is part of the COST action 3DForEcoTech [3DForEcoTech](https://3dforecotech.eu/) and co-funded by SmartForest [SmartForest](https://smartforest.no/)

![beech_spruce_pine](https://user-images.githubusercontent.com/5663984/205514849-14d77df2-0441-4caa-b230-6fdbdaad4ddc.png)

# What is the study case about
In this [google doc](https://docs.google.com/document/d/1ZbccmFbWLmyGxzJlcaE7QMqwauBFxgBb3gTPkEImuwg/edit) you can find an initial idea of the study case.

Overall, in this acitivity we should:
 - Provide a **benchmark dataset** for **developing** new point cloud classification models and **evaluating** existing methods.
 - Benchmark several methods (data science competition)
 - Publish the best models, code, the data, and of course a nice paper :)

# Available data sources (approx. 20K trees)
## Datasets
In this [google sheet](https://docs.google.com/spreadsheets/d/1qxj27Yh8B33I5eS9MAO9V_PJsr9OxU-kN3pY4TSlWHY/edit?usp=sharing)  sheet you can find some metadata regarding the available datasets. 

| dataset_name  | n_trees | n_species | data_type | Sensor | acquisition | annotation_quality | forest_type | x | y |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| wieser_TLS  | 264 | 12 | TLS | RIEGL VZ-400 | 15 scans per ha | manual | temperate | 14.7073 | 48.6638 |
| ...  | ... | ... | ... | ... | ... | ... | ... | ... | ... |

![Capture](https://user-images.githubusercontent.com/5663984/205518571-e7d85b0d-79ae-4dae-98da-99a1c4d7ff79.PNG)


## Trees 
Tree metadata can be found in this [google sheet](https://docs.google.com/spreadsheets/d/1zOk9QKjz9j-8_QKqzl1kNqKImPl9e9snVPHjyCu3AE8/edit?usp=sharing) containing the following information

| filename  | species | genus | dataset_name | data_type | tree_H |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | 
| tree_1.las  | Picea_abies | Picea | wieser_TLS | TLS | 15.5 | 
| ...  | ... | ... | ... | ... | ... | ... | 

### Tree distribution by tree species (33 tree species with more than 50 trees)
![species](https://user-images.githubusercontent.com/5663984/205514818-7af03617-e358-44e0-9f40-4c555d6bf3c5.png)

### Tree distribution by genus
![genus](https://user-images.githubusercontent.com/5663984/205514824-9c84acfb-e907-4bc7-8b10-ccff19bad82a.png)

### Tree height (m) distribution by tree species
![species_size](https://user-images.githubusercontent.com/5663984/205514870-8d1ca47f-9fdc-4a70-8a4f-cf197653a58c.png)

# Data science competition (Nov 2022 - Apr 2023)
The data will be organized as follows:
- point_clouds
-------------- tree_1.las 
-------------- tree_2.las 

- labels
-------- tree_metadata_treeSP_proximalLS.csv 

# output
- jupyter notebook for model training and inference
- .csv file with prediction for the test set with the following columns

| filename  | species | 
| ------------- | ------------- | 
| SOR_366.txt  | Picea_abies |  
| ...  | ... |

# evaluation
- Overall accuracy, precision, recall, F1-score
- number of species classified with accuracy > .5
 

# Global Vs regional models
- Boreal: Picea abies, Pinus sylvestris, Betula pendula 
- Boreal+: Picea abies, Pinus sylvestris, Betula pendula, Fagus sylvatica, Quercus sp., Acer sp., Tilia sp., Fraxinus exclesior
- Temperate: Picea abies, Pinus sylvestris, Betula pendula, Fagus sylvatica, Quercus sp., Acer sp., Carpinus betulus, Pseudotsuga mentziesii, Tilia cordata, Ulmus, Prunus, Crategous, Larix)
- Australia: Eucaliptus sp.
