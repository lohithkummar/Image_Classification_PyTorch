# Plant Disease Classification in Pytorch
## Description
This project demonstrates training and inference for an image classification model using Transfer Learning. The model is designed to classify images into predefined categories and was developed using PyTorch.

Installation
To set up the project on your local machine, follow these steps:
**1. Clone the repository**
```python
git clone https://github.com/lohithkummar/Plant-Disease-Classification-in-PyTorch.git
```
**2. Change Directories**
```python
  cd Plant-Disease-Classification-in-PyTorch
```
**3. Create and activate a virtual environment:**
```python
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```
**4. Install the required dependencies:**
```python
pip install -r requirements.txt
```

**5. Dataset Folder structure**
```
data/
├── train/
│   ├── Bacterial_spot/
│   ├── Black_mold/
│   └── ...
└── val/
├── Bacterial_spot/
├── Black_mold/
└── ...
```
### Disease list
The system uses an EfficientNet-B0 model trained on a dataset of tomato plant images to classify 7 different conditions:

- Bacterial spot
- Black mold
- Early blight
- Healthy
- Late blight
- Mosaic virus
- Septoria spot


## Usage
### Model Training
To train the model, you need to prepare your dataset and follow the steps below:

**1. Data Preparation:**

Organize your dataset into train and val directories. Each class should have its sub-directory within these folders.
Update the data_dir variable in the train-the-model.py script to point to your dataset directory.
**2. Training the model**
```python
python train-the-model.py
```
## Inference
To perform inference using the trained model:

**1. Prepare the Inference Script:**

Ensure you have a trained model checkpoint saved.
Update the script inference.py with the path to your checkpoint file.

**2. Running the inference**
```python
python inference.py --input_path /path/to/your/image.jpg
```

## Model Training
The training script train-the-model.py includes the following steps:

**1. Data Augmentation and Normalization:**

- Training data undergoes random resizing, cropping, and horizontal flipping.
- Validation data is resized and center-cropped.

**2. Model Setup:**

- EfficientNetB0 is used as the base model.
- The final classification layer is modified to match the number of target classes.

**3. Training Process:**

- The model is trained for a specified number of epochs with an initial learning rate of 0.001.
- The learning rate is decayed by a factor of 0.1 every 7 epochs.
- Training and validation accuracies and losses are printed for each epoch.
- 
## Inference
The inference script inference.py loads a trained model and performs predictions on a given input image. The script handles preprocessing of the input image, model inference, and post-processing of the output to display the predicted class.

## Results
The best model achieved an accuracy of 86.57% on the validation set. Detailed training logs and accuracy/loss plots can be found in the logs directory.

## Contributing
Contributions are welcome! Please fork the repository and submit a pull request for any enhancements or bug fixes.

You can practice it with the following kaggle dataset: 
PlantVillage: https://www.kaggle.com/datasets/abdallahalidev/plantvillage-dataset

