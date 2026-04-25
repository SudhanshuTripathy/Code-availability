# Code-availability for NSL-KDD Dataset for Zero-day attack detection
Enhancing Anomaly-Based Zero-Day Attack Detection Framework Using CNN-Driven Feature Extraction and OC-SVM
Final Steps to Run the Code (Google Colab)
Follow these steps carefully to execute the proposed CNN + OC-SVM model for intrusion detection:
Step 1: Open the Notebook
Open Google Colab
Upload or open the file:
CNN-OC-SVM-NSL-KDD.ipynb
Step 2: Set Runtime Environment
Go to Runtime → Change runtime type
Select:
Python 3
GPU (recommended for faster training)
Step 3: Run Library Import Cell
Execute the first cell
This loads all required libraries:
NumPy, Pandas
Scikit-learn
TensorFlow/Keras
Matplotlib/Seaborn
Step 4: Upload or Load Dataset
Upload NSL-KDD dataset files:
KDDTrain+.txt
KDDTest+.txt
OR mount Google Drive and load dataset from there
Step 5: Load and Prepare Data
Run the data loading cell
Assign column names to the dataset
Verify dataset is correctly loaded
Step 6: Perform Data Preprocessing
Encode categorical features (protocol, service, flag)
Normalize numerical features
Convert labels into binary:
Normal → 0
Attack → 1
Step 7: Split Features and Labels
Separate input features (X) and target labels (y)
Prepare training and testing datasets
Step 8: Reshape Data for CNN
Convert input data into 3D format:
(samples, features, 1)
This is required for Conv1D layers
Step 9: Build the CNN Model
Define CNN architecture:
Conv1D layers (feature extraction)
MaxPooling layers
Dropout (reduce overfitting)
Dense layers
Sigmoid output layer
Step 10: Compile and Train CNN
Compile model using:
Optimizer: Adam
Loss: Binary Crossentropy
Train the model on training data
Step 11: Extract Deep Features
Use the trained CNN model
Extract features from an intermediate layer
These features represent learned patterns in network traffic
Step 12: Train OC-SVM Model
Train One-Class SVM using only normal data
Set kernel (e.g., RBF) and parameters (gamma, nu)
Step 13: Perform Prediction
Apply OC-SVM on test data
Convert output:
+1 → Normal
-1 → Attack
Step 14: Evaluate Model Performance
Generate performance metrics:
Accuracy
Precision
Recall
F1-score
Step 15: Display Final Results
Results are shown in output cells
Metrics and graphs demonstrate model performance
Important Instructions
Run all cells sequentially (top to bottom)
Do not skip any step
Ensure dataset is uploaded before execution
Use same parameters for reproducibility


#  Code-availability for CIC-IDS2017 Dataset for Zero-day attack detection

