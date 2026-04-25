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
Step 1: Open the Notebook in Google Colab
Open Google Colab
Upload or open the notebook:
CNN-OCSVM-CIC_IDS_2017_Friday_portscan_Botnet_DDoS.ipynb
Step 2: Configure Runtime
Go to Runtime → Change runtime type
Select:
Runtime type: Python 3
Hardware accelerator: GPU (recommended)
Step 3: Import Required Libraries
Run the first cell
This loads:
NumPy, Pandas
Scikit-learn
TensorFlow/Keras
Matplotlib, Seaborn
If any library is missing:
!pip install numpy pandas scikit-learn tensorflow matplotlib seaborn
Step 4: Upload or Load Dataset
Upload the CIC-IDS2017 dataset file (Friday dataset: PortScan, Botnet, DDoS)
OR mount Google Drive:
from google.colab import drive
drive.mount('/content/drive')
Load dataset using Pandas:
data = pd.read_csv('your_dataset.csv')
Step 5: Data Cleaning and Preparation
Remove unnecessary or null values
Handle missing/infinite values
Rename columns if required
This ensures clean and usable input data.
Step 6: Label Processing
Convert multi-class labels into binary:
Normal → 0
Attack → 1
Required for OC-SVM anomaly detection
Step 7: Feature Scaling
Normalize numerical features using:
StandardScaler or MinMaxScaler
Important for both CNN and OC-SVM performance.
Step 8: Split Features and Labels
Separate:
X → Features
y → Labels
Split into training and testing datasets
Step 9: Reshape Data for CNN
Convert input into 3D format:
(samples, features, 1)
Required for Conv1D layers.
Step 10: Build CNN Model
Define CNN architecture:
Conv1D layers (extract temporal patterns)
MaxPooling layers
Dropout (0.5) for regularization
Dense layers
Sigmoid output
Step 11: Compile CNN Model
Optimizer: Adam
Loss: Binary Crossentropy
Metrics: Accuracy, Precission, Recall, F1-score
Step 12: Train CNN Model
Train model using training data:
model.fit(X_train, y_train, epochs=..., batch_size=...)
Step 13: Extract Deep Features
Use intermediate CNN layer output
Convert raw data into high-level feature vectors
These features are used as input to OC-SVM.
Step 14: Train OC-SVM
Train One-Class SVM:
Use only normal samples
Define:
Kernel (rbf / linear / poly / sigmoid)
Gamma
ν (nu parameter)
Step 15: Perform Prediction
Apply OC-SVM on test features
Output:
+1 → Normal
-1 → Attack
Convert to binary labels if needed
Step 16: Evaluate Performance
Generate evaluation metrics:
Accuracy
Precision
Recall
F1-score
Typically using:
from sklearn.metrics import classification_report
Step 19: Display Final Results
All outputs appear in notebook:
Metrics
Graphs
Performance summary
Important Instructions
Run all cells sequentially (top → bottom)
Do not skip any cell
Ensure dataset path is correct
Use same parameters for reproducibility
GPU is recommended for faster CNN training
