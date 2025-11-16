# Potato Disease Classification

A deep learning-based solution to help farmers identify early blight, late blight, and healthy potato plants, enabling early intervention and reducing economic losses.

## 🧠 Project Overview

Potato farmers face significant economic threats from plant diseases, primarily **Early Blight** (fungal) and **Late Blight** (water mold). Accurate and early detection is crucial, as the treatment for each disease differs.

This project, in collaboration with **AtliQ Agriculture**, delivers a scalable system where a farmer can simply take a photo of a potato plant with a mobile app and instantly receive a diagnosis (label and confidence score).

The end-to-end workflow encompasses deep learning model development, MLOps, backend API creation, and deployment to Google Cloud Platform for mobile application integration.

## 🚀 Tech Stack

*   **Model Building & ML Ops:** TensorFlow / Keras, CNN, Data Augmentation, TF Dataset, TF Serving, Quantization, TensorFlow Lite
*   **Backend & API:** FastAPI
*   **Frontend & Mobile:** React.js (Web App), React Native (Mobile App)
*   **Cloud & Deployment:** Google Cloud Platform (GCP), Google Cloud Functions

## ⚙️ System Architecture & Workflow

1.  **Data Collection & Preparation:**
    *   Collected images of potato leaves categorized into three classes: `Healthy`, `Early Blight`, and `Late Blight`.
    *   Performed data cleaning, preprocessing, and augmentation (rotations, flips, contrast adjustments) using `tf.data` to enhance model robustness.

2.  **Model Building & Training:**
    *   Built a Convolutional Neural Network (CNN) using TensorFlow for image classification.
    *   Trained the model on the preprocessed dataset to distinguish between the three classes.

3.  **ML Ops & Backend Serving (Web):**
    *   Exported the trained TensorFlow model.
    *   Served the model using **TensorFlow Serving** for high-performance inference.
    *   Built a **FastAPI** backend server to interface between clients and the TF Serving model.
    *   Developed a React.js web application for testing, allowing users to drag-and-drop images for instant predictions.

4.  **Model Optimization for Mobile:**
    *   Converted the full-precision model to a **TensorFlow Lite** model using **Quantization**.
    *   This significantly reduces model size and accelerates inference speed, making it ideal for mobile and edge devices.

5.  **Cloud Deployment & Mobile Integration:**
    *   Deployed the optimized TFLite model to **Google Cloud Platform (GCP)**.
    *   Wrote serverless **Google Cloud Functions** to handle prediction requests.
    *   A **React Native** mobile app calls these cloud functions, allowing farmers to get diagnoses in real-time from the field.

## 📁 Project Structure
potato-disease-classification/
├── data/ # Dataset and preprocessing scripts
├── model/ # Model training scripts and exported models
├── tf-serving/ # Configuration for TensorFlow Serving
├── backend/ # FastAPI server code
├── web-app/ # React.js frontend source
├── mobile-app/ # React Native application source
├── cloud-functions/ # Google Cloud Function code
└── README.md


## 🛠️ Installation & Usage

*(This section would be filled with specific commands for cloning, installing dependencies, and running different parts of the project.)*

**Prerequisites:** Python, Node.js, TensorFlow, etc.

### Running the Web Application Locally

1.  **Start the TF Serving Container:**
    ```bash
    docker run ... # TF Serving command
    ```
2.  **Start the FastAPI Backend:**
    ```bash
    cd backend
    uvicorn main:app --reload
    ```
3.  **Start the React Frontend:**
    ```bash
    cd web-app
    npm start
    ```
4.  Open `http://localhost:3000` and upload a potato leaf image.

## 👨‍🌾 Mobile Application

The React Native mobile app provides a simple interface for farmers. Point the camera at a leaf, take a picture, and get an immediate diagnosis to guide treatment decisions.

## 🙏 Acknowledgments

*   AtliQ Agriculture for the problem statement and collaboration.
*   The providers of the public potato disease dataset.