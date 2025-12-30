 AI-Powered Crop Disease Detection System
📌 Project Overview

 AI is an AI-based web application that detects crop diseases from leaf images using deep learning models (CNN & ResNet-50).
The system provides instant disease prediction, confidence score, severity level, and treatment recommendations, helping farmers take timely action and reduce crop losses.

🎯 Aim of the Project

Develop an automated crop disease detection system using AI

Classify crop leaf images as healthy or diseased

Provide fast and accurate diagnosis

Support sustainable farming practices

🖼️ System Architecture / Output Preview

📌 Place this image in your GitHub repository
Example path: assets/system_architecture.png or images/output.png

![CropGuard AI System Architecture](assets/system_architecture.png)


📌 You can also center it:

<p align="center">
  <img src="assets/system_architecture.png" width="700"/>
</p>

🧠 Algorithms Used
1. Convolutional Neural Network (CNN)

Extracts visual features like color, texture, and disease spots

Performs feature extraction and classification

Efficient for image-based tasks

2. ResNet-50 (Transfer Learning)

50-layer deep residual network

Uses skip connections to prevent vanishing gradients

Pretrained on ImageNet for better accuracy

🔁 Algorithm Workflow
![Workflow Diagram](assets/workflow.png)


Image upload by user

Image preprocessing

Feature extraction

Disease classification

Result display

💻 Sample Code
from fastapi import FastAPI, UploadFile, File
from PIL import Image
import io

app = FastAPI()

@app.post("/predict")
async def predict_disease(file: UploadFile = File(...)):
    image = Image.open(io.BytesIO(await file.read()))
    return {
        "disease": "Early Blight",
        "confidence": "94%",
        "severity": "Moderate"
    }

📊 Output
![Prediction Output](assets/output.png)

Example Result:

Disease: Early Blight

Confidence: 94%

Severity: Moderate

Treatment: Apply fungicide and remove affected leaves
