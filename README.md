# Code-availability
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
