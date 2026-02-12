Car Damage Detection using Deep Learning

A deep learning–based web application that classifies vehicle damage from images using a ResNet50 model and a Streamlit interface.
Users can upload a car image, and the app predicts the type and location of damage (front/rear, crushed/breakage/normal).
<img width="903" height="784" alt="image" src="https://github.com/user-attachments/assets/62547131-4c23-4001-823d-475f6241b2fa" />
<img width="890" height="793" alt="image" src="https://github.com/user-attachments/assets/d8e8d3c7-e61a-4590-95c6-281fee46d92f" />

Tech Stack:
Python 3.13
PyTorch
Torchvision
Streamlit
Pillow, NumPy, Pandas

📂 Project Structure
streamlit-app/
│── app.py                 # Streamlit UI
│── model_helper.py        # Model loading & prediction logic
│── saved_model.pth        # Trained model weights
│── requirements.txt       # Dependencies
│── *.ipynb                # Training / experiments
│── temp_file.jpg          # Temporary uploaded image


Mini Flowchart (App Pipeline):

[ User Uploads Image ]
            |
            v
      [ Streamlit UI ]
            |
            v
   [ Save temp image file ]
            |
            v
   [ Load ResNet50 model ]
            |
            v
 [ Preprocess Image (224x224, Normalize) ]
            |
            v
     [ Model Inference ]
            |
            v
   [ Predicted Damage Class ]
            |
            v
     [ Display Result ]


⚙️ How It Works

User uploads an image through the Streamlit interface.
The image is saved temporarily.
The trained ResNet50 model is loaded.
The image is preprocessed (resize, tensor conversion, normalization).
The model runs inference using PyTorch.
The predicted damage class is displayed on the UI.

🏷️ Classes Predicted
Front Breakage
Front Crushed
Front Normal
Rear Breakage
Rear Crushed
Rear Normal

Installation & Run:
1. Clone the repository
git clone https://github.com/Hritik123789/Car-Damage-Detection-Project.git
cd Car-Damage-Detection-Project

2. (Optional) Create virtual environment
py -3.13 -m venv venv
venv\Scripts\activate

3. Install dependencies
py -3.13 -m pip install -r requirements.txt

4. Run the app
py -3.13 -m streamlit run app.py

Usage:

Open the Streamlit URL shown in the terminal.

Upload a .jpg, .jpeg, or .png image of a car.

The app will display the uploaded image and the predicted damage class.

Notes:

The model uses transfer learning with ResNet50.

Only the final layers are fine-tuned for damage classification.

Make sure saved_model.pth is present in the project directory (or download it if hosted externally).

requirements.txt contains the required dependencies.
