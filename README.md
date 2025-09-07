# Potato-Disease-Classification

A deep learning project to classify potato plant diseases using image datasets. The system is built with a trained model and a FastAPI backend for deployment.

---

## 📌 Project Overview
This project aims to detect and classify potato diseases from leaf images.  
It uses the **PlantVillage dataset** and a trained deep learning model to predict whether a potato plant is healthy or affected by a disease such as **Early Blight** or **Late Blight**.  

The backend is implemented with **Flask**, allowing model inference via API endpoints.

---

## 📂 Repository Contents
- `trainingmodel-checkpoint.ipynb` — Jupyter notebook for training the model.  
- `main1.py` — FastAPI backend file for serving predictions.  
- `saved_model/` — Directory for storing the trained model.  
- `requirements.txt` — List of required dependencies.  

---

## 📊 Dataset
The dataset is available on Kaggle:  
👉 [PlantVillage Dataset](https://www.kaggle.com/datasets/arjuntejaswi/plant-village)  

It contains **54,000+ labeled images** of plant leaves from 14 crop species with 26 diseases. For this project, the potato subset is used.

---

## 🚀 Steps to Run the Project

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/Gauravmangate27/Potato-disease-classification.git
cd Potato-disease-classification
