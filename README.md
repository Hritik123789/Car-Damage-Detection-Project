# Vehicle Damage Detection

A deep learning-based web application for detecting and classifying vehicle damage using Streamlit and PyTorch.

## Features

- **Image Upload**: Upload vehicle images (JPG, JPEG, PNG)
- **AI-Powered Detection**: Uses ResNet50 deep learning model for accurate damage classification
- **6 Damage Classes**: 
  - Front Breakage
  - Front Crushed
  - Front Normal
  - Rear Breakage
  - Rear Crushed
  - Rear Normal
- **Real-Time Predictions**: Instant damage classification and visual feedback

## Requirements

- Python 3.8+
- PyTorch 2.9.0
- Streamlit 1.48.1
- Pillow 12.1.1
- torchvision 0.24.0

## Installation

1. Clone or download this repository

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Ensure the pre-trained model is in the `model/` directory:
```
model/
  └── saved_model.pth
```

## Usage

Run the Streamlit app:

```bash
streamlit run app.py
```

The app will open in your default web browser at `http://localhost:8501`

### Steps to use:

1. Click "Upload the file" button
2. Select a vehicle image (JPG, JPEG, or PNG format)
3. The image will be displayed along with the AI prediction
4. The predicted damage class will be shown

## Model Architecture

- **Base Model**: ResNet50 (pre-trained on ImageNet)
- **Fine-tuning**: Layer4 and final fully connected layer are trainable
- **Input Size**: 224x224 pixels
- **Output**: 6 damage classification classes
- **Dropout Rate**: 0.2 for regularization

## Project Structure

```
streamlit-app/
├── app.py                 # Main Streamlit application
├── model_helper.py        # Model loading and prediction logic
├── requirements.txt       # Python dependencies
├── README.md             # This file
└── model/
    └── saved_model.pth   # Pre-trained model weights
```

## Files Overview

- **app.py**: Streamlit UI for uploading images and displaying predictions
- **model_helper.py**: Contains the CarClassifierResNet model and prediction pipeline
- **saved_model.pth**: Pre-trained model weights (ResNet50 fine-tuned for damage classification)

## Technical Details

### Image Preprocessing

- Resize to 224x224 pixels
- Convert to tensor
- Normalize using ImageNet statistics (mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225])

### Model Implementation

The `CarClassifierResNet` class implements a modified ResNet50 architecture:
- Freezes most pre-trained layers
- Unfreezes Layer4 for fine-tuning
- Replaces final FC layer with custom 6-class classifier
- Includes dropout for regularization

## Getting Started

For best results, use clear, well-lit images of the vehicle damage area. The model is optimized for front and rear damage classification from multiple angles and lighting conditions.

---

For issues or questions, refer to the main project repository and documentation.
