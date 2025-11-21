# Virus CGR Project (Draft)

This repository contains the draft submission for the Bioinformatics Project:
**Alignment-Free Virus Family Classification Using Chaos Game Representation (CGR).**

##  Repository Structure
- `notebook/virus_cgr_classification.ipynb`  
  Full notebook used to download genomes, generate CGR images, train XGBoost and ResNet18 models, and produce all figures.

- `figures/`  
  - `resnet18_confusion_matrix.png`  
  - `resnet18_gradcam_example.png`

- `ai_usage.md`  
  Documentation describing how AI tools were used and how outputs were verified.

- `requirements.txt`  
  Python package list for reproducibility.

##  Project Summary
This project classifies viral genomes into families using alignment-free CGR images and machine learning models.

**Models implemented:**
- XGBoost on 6-mer frequency vectors  
- ResNet18 on CGR images  
- Grad-CAM for CNN interpretability  

##  How to Run
Open the notebook in Google Colab and run all cells in order.

Final results (accuracy, macro-F1, confusion matrix, Grad-CAM) will appear automatically.

## 📦 Data Source

Viral genome sequences were obtained from the **NCBI RefSeq Viral Genome Database**:

https://www.ncbi.nlm.nih.gov/refseq/targetedloci/viral/

The dataset consists of 664 complete reference genomes across multiple viral families.  
The data is **not stored in the repository** due to file size, but is downloaded automatically using Biopython's Entrez utilities inside the notebook:

```python
from Bio import Entrez
Entrez.email = "your_email@example.com"
handle = Entrez.esearch(db="nuccore", term="Adenoviridae[Organism] AND complete genome")


Genomes are downloaded automatically through the notebook (Biopython Entrez).

## Status (Draft)
- All core analyses completed  
- Figures generated  
- Draft report submitted  
- Final report will include additional metrics, more Grad-CAM examples, and hyperparameter tuning
