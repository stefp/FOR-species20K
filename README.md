
# Benchmarking tree species classification from proximally sensed laser scanning data: Introducing the FOR-species20K dataset 🌳🌲💥🤖
Repository for the study by [Puliti et al. (2025)](https://besjournals.onlinelibrary.wiley.com/doi/full/10.1111/2041-210X.14503) to benchmark tree species classification using proximally sensed laser scanning data (TLS, MLS, ULS). This work is part of the COST action 3DForEcoTech [3DForEcoTech](https://3dforecotech.eu/) and co-funded by [SmartForest](https://smartforest.no/). To cite this work use:

_Puliti, S., Lines, E. R., Müllerová, J., Frey, J., Schindler, Z., Straker, A., Allen, M. J., Winiwarter, L., Rehush, N., Hristova, H., Murray, B., Calders, K., Coops, N., Höfle, B., Irwin, L., Junttila, S., Krůček, M., Krok, G., Král, K., … Astrup, R. (2025). Benchmarking tree species classification from proximally sensed laser scanning data: Introducing the FOR-species20K dataset. Methods in Ecology and Evolution, 00, 1–18. https://doi.org/10.1111/2041-210X.14503_

![beech_spruce_pine](https://user-images.githubusercontent.com/5663984/205514849-14d77df2-0441-4caa-b230-6fdbdaad4ddc.png)

# What is the study case about
The overall aim consists of developing a **benchmark dataset** for **developing** new point cloud tree species classification models and **benchmarking** them

# Available data sources (approx. 20K trees 🤯)
## Datasets
The FOR-species20K data can be downloaded from the [Zenodo repository](https://zenodo.org/records/13255198)

Below you can find some metadata regarding the available datasets.

| dataset_name  | n_trees | n_species | data_type | Sensor | acquisition | annotation_quality | forest_type | x | y |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| wieser_TLS  | 264 | 12 | TLS | RIEGL VZ-400 | 15 scans per ha | manual | temperate | 14.7073 | 48.6638 |
| ...  | ... | ... | ... | ... | ... | ... | ... | ... | ... |

![figure_1](https://github.com/user-attachments/assets/e248bafb-2f53-40bb-ac30-ce75ff5a1fb6)


## Trees 
Tree metadata can be found in the tree_metadata_training_publish.csv. Each row represents a single tree with the following fields:

| treeID  | species | genus | dataset | data_type | tree_H | filename |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | 
| 1  | Picea_abies | Picea | wieser_TLS | TLS | 15.5 | /train/00070.las |
| ...  | ... | ... | ... | ... | ... | ... | ... | 

the "tree_H" variable is simply the difference between the top and bottom z value for each tree and should be used only to get a rough understanding of tree size, however keep in mind that this does NOT necessarily correspond to the real tree height.

### Tree distribution by tree species (33 tree species with more than 50 trees)
![figure_3](https://github.com/user-attachments/assets/3c88db2d-e0b2-4324-81f1-3e4a33f3a156)

# Data science competition (Nov 2022 - May 2023) 🏎️ 
The data science competition will run from Jan 2023 to Apr/May 2023. Each contributor will be able to make a maximum of 3 submissions.

To make a submission should send me (stefano.puliti@nibio.no) a csv file with predictions on the test dataset and with the following two columns:
| treeID  | predicted_species | 
| ------------- | ------------- | 
| 523  | Pinus_sylvestris |  
| ...  | ... |

# Leader board 🏁

| ranking | Author | Institution  | Overall accuracy | Precision | Recall | F1-score | method |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| 1 | Julian Frey & Zoe Schindler | University of Freiburg | 0.79 | 0.81 | 0.79 | 0.79 | DetailView [github repo](https://github.com/JulFrey/DetailView) |
| 2 | Adrian Straker | University of Goettingen | 0.78 | 0.81 | 0.78 | 0.78 | YOLOv5 [github repo](https://github.com/AWF-GAUG/Yolov5-for-tree-species-classification-in-point-cloud-derived-images) |
| 3 | Matt Allen | University of Cambridge | 0.76 | 0.77 | 0.76 | 0.76 | SimpleView [github repo](https://github.com/mataln/TLSpecies) |
| 4 | Lukas Winiwarter | UBC/TU Wien | 0.76 | 0.77 | 0.76 | 0.75 | PointNet++ [github repo](https://github.com/lwiniwar/Tr3D_species_lwiniwar) |
| 5 | Nataliia Rehush | WSL | 0.74 | 0.77 | 0.74 | 0.73 | MinkNet [github repo](https://github.com/nrehush/minknet-tree-species) |
| 6 | Hristina Hristova & Nataliia Rehush | WSL | 0.71 | 0.72 | 0.71 | 0.7 | MLP-Mixer [github repo](https://github.com/Hrisi/tree-species-classification) |
| 7 | Brent Murray | UBC | 0.68 | 0.67 | 0.68 | 0.67 | PointAugment + DGCNN  [github repo](https://github.com/Brent-Murray/TR3D_PointAugDGCNN) |


# Confusion matrix of top performing method 📈

![figure_5](https://github.com/user-attachments/assets/fe78e4aa-f8b5-4ec5-89d5-76cfc4016c92)

# Want to enter the leaderboard? 🏆 Benchmark your model against the withheld test data
Any user can benchamrk their own model against the withheld test data in [FOR-species20K Codabench page](https://www.codabench.org/competitions/3667/). Give it a try, it works like a charm 🥳





