# OCR Text Recognition with CRNN and Django Backend

This project implements an Optical Character Recognition (OCR) system for recognizing Arabic text in images. The system uses a Convolutional Recurrent Neural Network (CRNN) for text recognition and provides an API for text prediction through a Django backend.

## Table of Contents

1. [Project Overview](#project-overview)
2. [Data Preprocessing](#data-preprocessing)
3. [Model Building and Training](#model-building-and-training)
4. [Model Conversion to ONNX](#model-conversion-to-onnx)
5. [Django Backend Setup](#django-backend-setup)
6. [API Testing](#api-testing)
7. [Installation](#installation)
8. [Usage](#usage)
9. [Acknowledgements](#acknowledgements)

## Project Overview

The OCR system consists of several steps:
- Preprocessing the data
- Building and training the CRNN model
- Converting the trained model to ONNX format
- Setting up a Django backend to serve the model
- Testing the API endpoint with a client script

## Data Preprocessing

The data preprocessing pipeline includes the following steps:
1. **Load and filter image and text files** from the dataset directory.
2. **Preprocess images**: Resize and normalize the images.
3. **Convert text to sequences**: Map characters to integers and pad the sequences.
4. **Save preprocessed data**: Save images and labels as NumPy arrays.

## Model Building and Training

The CRNN model architecture consists of:
- Convolutional layers for feature extraction
- Bidirectional LSTM layers for sequence modeling
- Dense output layer with softmax activation for classification

The model is trained using the CTC (Connectionist Temporal Classification) loss function.

## Model Conversion to ONNX

After training, the Keras model is converted to ONNX format using `tf2onnx` for efficient inference in the Django backend.

## Django Backend Setup

The Django backend serves the OCR model through an API endpoint:
1. **Install Django and necessary packages**.
2. **Create a Django project and app**.
3. **Configure settings and URLs**.
4. **Implement views** to handle image upload and text prediction.

## API Testing

A client script sends a POST request to the API endpoint with an image file and prints the predicted text.

## Usage

1. **Data Preprocessing**:
    - Ensure your dataset is located in the specified folder.
    - Run the preprocessing script to prepare the data.

2. **Model Training**:
    - Train the CRNN model using the provided training script.

3. **Model Conversion**:
    - Convert the trained Keras model to ONNX format.

4. **Django Backend**:
    - Start the Django development server.
    - Use the client script to test the API endpoint.

## Acknowledgements

- The CRNN model architecture is inspired by the paper "An End-to-End Trainable Neural Network for Image-based Sequence Recognition and Its Application to Scene Text Recognition".
- The Django framework is used for serving the OCR model.

---

For detailed instructions and code examples, please refer to the respective sections in the project documentation.
