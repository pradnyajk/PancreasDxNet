# PancreasDxNet
Pancreatic ductal adenocarcinoma (PDAC) is a highly aggressive malignancy with the five-year survival rate of only 13% largely due to late-stage diagnosis. Accurate and early detection is critical for improving survival outcomes.
Considering the importance and prevalence of pancreatic cancer worldwide, we trained an effective CNN-based multiclass classification model to classify computed tomography (CT) scan images of pancreas into three classes such as pancreatic cancer, pancreatitis and normal pancreas. The ResNet50-based CNN model achieved highest average accuracy of 99.26% and 99.16% on the validation and additional test set.

PancreasDxNet (Pancreatic Diagnosis Network) is a deep convolutional neural network designed for automated multi-class classification of pancreatic CT images into pancreatic cancer, pancreatitis, and normal pancreas.

---

## Package requirements:
* python = 3.12
* numpy
* pandas
* tensorflow = 2.18.0
* keras = 3.6.0
* scikit-learn
* scipy
* opencv-python

## Repository Structure
````
PancreasDxNet/
├── app.py                  # Streamlit application
├── requirements.txt        # Dependencies
├── utils/
│   └── model.py            # Preprocessing + prediction logic
├── Model/
│   └── generated_model.h5  # Trained CNN model
├── Training_scripts/       # Model training scripts
├── prediction_pc.py        # Script-based inference (legacy)
├── Images/                 # Sample/test images
└── README.md
````
---

## Usage

This repository supports two modes of prediction:

### Option 1: Script-Based Prediction

> **_NOTE:_** Remember to activate the corresponding conda environment before running the script, if applicable.

**Input**: Image file (image.jpg)

**Output**: predictions.csv

**Execution:**

**Step 1**: Install Git LFS
Install and initialize Git LFS before cloning the repository.
``git lfs install``

**Step 2**: Clone the Repository
Clone the repository using Git:
`git clone https://github.com/pradnyajk/PancreasDxNet.git`

Navigate to the repository:
`cd PancreasDxNet`

Download the large model file managed by Git LFS:

`git lfs pull`

Verify that the trained model has been downloaded correctly:

`ls -lh Model/generated_model.h5`

The file should be approximately 92 MB.

> **_NOTE:_** The Model/generated_model.h5 file must be the actual HDF5 model file. If the file contains text beginning with version https://git-lfs.github.com/spec/v1, the Git LFS model has not been downloaded correctly.

**Step 3**: Set Up the Python Environment
Install Anaconda3-5.2 or above.
Before running these scripts, create a new conda environment and install the following packages using the pip command (pip install name_of_package = version)
Install or upgrade libraries mentioned above (python, numpy, pandas, tensorflow, keras, scikit-learn, scipy).
Install Anaconda3-5.2 or above

```
conda create -n pcnn python=3.12
conda activate pcnn`
pip install -r requirements.txt
```
**Step 4**: Prepare the Input Images
Place the pancreatic CT images to be predicted in the Images folder.

**Step 5**: Run the Prediction Script
Execute:
`python prediction_pc.py`

The script automatically reads the images from the Images folder, preprocesses the images, loads the pretrained PancreasDxNet model, and generates predictions.

**Step 6**: View the Prediction Results

The prediction results are saved automatically as:

predictions.csv

The output file contains the predicted class and the corresponding prediction probabilities for each pancreatic CT image.
The three predicted classes are:
- Cancer
- Normal
- Pancreatitis
---

### Option 2: Streamlit Web App

Install all dependencies using:

    pip install -r requirements.txt

Run the interactive application:

    streamlit run app.py

Then open in browser:

http://localhost:8501

Steps:

Upload a CT scan image
Click Predict
View predicted class and probabilities

---

## Citation

If you use **PancreasDxNet** in your research, please cite:

```bibtex

```
---
