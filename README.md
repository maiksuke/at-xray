# Disease Detection from Chest X-rays

## Authors

-   Marttis Ladev
-   Raigo Leesment
-   Mairon Mihklesoo

## Motivation and goal

The primary motivation behind this project is to leverage automated image
analysis to assist in diagnosing various lung diseases from chest X-ray images:
Use machine learning methods to analyze chest X-rays and identify patterns
indicative of different diseases and Develop a model capable of accurately
classifying diseases and demonstrate

## Guide

This repository contains all the necessary components for training, validating,
and using a deep learning model for chest X-ray classification. Below is a
structured explanation of the repository contents:

---

### Folder and File Structure

#### 1. **Main Script (`main.ipynb`)**

-   **Purpose**: The central script for:
    -   Loading and preprocessing data
    -   Defining the model (using the ResNet50 base model)
    -   Training the model and saving checkpoints
    -   Loading a model from checkpoints

#### 2. **Checkpoint Directory (`model_checkpoints/`)**

-   **Contents**: Contains saved model weights and architecture for each epoch,
    for example:
    -   `model_epoch_001.keras`
    -   `model_epoch_002.keras`
-   **Purpose**: Enables resuming training from a specific point or loading a
    pre-trained model for inference.

#### 3. **Dataset Folder (`Chest X_Ray Dataset/`)**

-   **Contents**: Images organized into class-specific subfolders:
    ```
    Chest X_Ray Dataset/
    ├── COVID19/
    ├── NORMAL/
    ├── PNEUMONIA/
    └── TURBERCULOSIS/
    ```
-   **Purpose**: Provides the input data for training and validation. Each
    subfolder represents a class.

#### 4. **Model Architecture File (`model_architect.json`)**

-   **Contents**: Description of the model architecture, including the ResNet50
    base model and custom layers.
-   **Purpose**: Used to document or recreate the model configuration.

#### 5. **Prediction Script (`ennustus.ipynb`)**

-   **Purpose**: A script to utilize the trained model for making predictions on
    new data.
-   **Key Features**:
    -   Loads the trained model from a checkpoint
    -   Preprocesses input data (e.g., resizing and normalizing images)
    -   Generates predictions and visualizes results

---

### How to Use This Repository

#### 1. **Training the Model**

-   Run `main.ipynb` or the equivalent training script to:
    -   Preprocess the data
    -   Define the model
    -   Start training and save checkpoints

#### 2. **Loading and Resuming Training**

-   Use the checkpoint directory (`model_checkpoints/`) to load the model from a
    specific epoch. The `load_model_from_epoch` function facilitates this.

#### 3. **Making Predictions**

-   Execute `ennustus.ipynb` to load the trained model and make predictions on
    new datasets.

#### 4. **Customizing the Model**

-   Modify the architecture in `model_architect.json` to add new layers or
    adjust the existing structure.

#### 5. **Dataset Organization**

-   Ensure that all images are correctly organized into subfolders within the
    dataset directory. Each subfolder name should correspond to its respective
    class label.

## How to predict diseases from X-ray images with ennustus.ipynb code:

### Model availability:

The model should be saved in the model_checkpoints directory, e.g., as a file
model_epoch_955.keras.

### Image preparation:

Images should be in a folder named uued. They should be in standard formats such
as .jpg or .png.

### Required libraries:

### Install the necessary Python packages:

bash Copy code pip install tensorflow numpy pillow

### Code functionality:

The script: Loads the model and images. Normalizes the images. Makes predictions
for each image (COVID-19, NORMAL, PNEUMONIA, TUBERCULOSIS) and shows the
probabilities.

### Displaying results:

The predictions are printed in the terminal, showing the image name, predicted
label, and the probability for the main prediction.
