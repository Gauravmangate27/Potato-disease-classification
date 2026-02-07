# Potato Disease Classification

A deep learning project for classifying potato plant diseases from leaf images using the PlantVillage dataset. The system includes model training, evaluation, and a FastAPI backend for serving predictions via API.

Repository: https://github.com/Gauravmangate27/Potato-disease-classification

## Overview

This project develops a convolutional neural network (CNN) to detect and classify diseases in potato plants based on leaf photographs. It identifies three classes:

- Healthy  
- Early Blight (caused by Alternaria solani)  
- Late Blight (caused by Phytophthora infestans)  

The model is trained on a subset of the PlantVillage dataset and deployed via a FastAPI backend, enabling inference through HTTP requests. This can support applications in precision agriculture, early disease detection, and automated crop monitoring.

**Disclaimer**  
This project is for educational, research, and demonstration purposes only. It is not intended for production use in critical agricultural decision-making without further validation, field testing, and expert oversight.

## Dataset

The model uses the potato subset from the **PlantVillage Dataset**, a widely-used public benchmark for plant disease classification.

- Source: [Kaggle - PlantVillage Dataset](https://www.kaggle.com/datasets/abdallahalidev/plantvillage-dataset) (or similar mirrored versions)  
- Potato classes & approximate counts:  
  - Potato___Early_blight: ~1,000 images  
  - Potato___Late_blight: ~1,000 images  
  - Potato___healthy: ~152 images  
- Total potato images: ~2,152  
- Image characteristics: 256×256 pixels (typically), RGB, lab-collected (controlled background)  

**Note**: Download the full dataset from Kaggle, extract only the potato-related folders, and organize into train/validation/test splits as needed before training.

## Features

- Multi-class image classification using TensorFlow/Keras  
- Data preprocessing: resizing, normalization, augmentation  
- Model training and evaluation (accuracy, precision, recall, F1-score, confusion matrix)  
- FastAPI backend for RESTful inference  
- Simple API endpoint to upload an image and receive class prediction + confidence  

## Project Structure
<img width="842" height="287" alt="image" src="https://github.com/user-attachments/assets/de48dc89-eb61-4bf6-babe-a98786dfa478" />

## Technologies Used

- Python 3.8+  
- TensorFlow / Keras (deep learning framework)  
- FastAPI (API backend)  
- Uvicorn (ASGI server)  
- Pillow / OpenCV (image processing)  
- NumPy, Matplotlib (data handling & visualization)  

See `requirements.txt` for the full list.

## Getting Started

### Prerequisites

- Python 3.8 or higher  
- Git  
- (Optional) Virtual environment tool (venv, conda)  

### Installation

1. Clone the repository
   ```bash
   git clone https://github.com/Gauravmangate27/Potato-disease-classification.git
   cd Potato-disease-classification
2.	Create and activate a virtual environment (recommended)
   <img width="652" height="154" alt="image" src="https://github.com/user-attachments/assets/71788b7f-73eb-4d40-ad3a-5a44af4eb6de" />
    1.Install dependencies
 
  	pip install -r requirements.txt
Running the API Server

1.Ensure the trained model is present in saved_model/ (or retrain using the notebook)
2.Start the FastAPI server
<img width="409" height="116" alt="image" src="https://github.com/user-attachments/assets/3290939b-3769-4877-8827-54f8291651a2" />
3.Open your browser and navigate to:
http://127.0.0.1:8000/docs
(Interactive Swagger UI for testing the API)

4.Model Training (Optional / Reproduce)

  1.Download and prepare the PlantVillage potato subset
  2.Open trainingmodel-checkpoint.ipynb in Jupyter
  3.Execute cells sequentially: load data → preprocess → build/train model → evaluate → export
  4.The saved model will be placed in saved_model/

5.API Usage Example
  
    1.Endpoint: POST /predict
    
    2.Content-Type: multipart/form-data
    
    3.Form field: file (upload a leaf image: .jpg, .png, etc.)

Example with curl:

<img width="482" height="166" alt="image" src="https://github.com/user-attachments/assets/133c74dd-131f-4928-8312-1cad298ff425" />
<img width="596" height="258" alt="image" src="https://github.com/user-attachments/assets/4da5000a-09c6-47f0-ab06-350b677be32a" />
  
5.Performance Notes
  Typical results on this dataset (depending on architecture, augmentation, and splits):
  
    1.Accuracy: 95–98%+ on validation/test sets
    2.Common architectures: Custom CNN, MobileNetV2, EfficientNet (transfer learning often yields better generalization)
  
  Detailed metrics, training curves, and confusion matrices are available in the training notebook.


