# Customer Churn Prediction using Neural Networks

## Project Overview
This project focuses on building and analyzing a neural network model to predict customer churn using a structured dataset. The primary goal is to address the challenges posed by class imbalance in churn prediction and to understand the impact of various hyperparameter choices on model performance.

## Dataset
*   **Name:** `customer_churn_nn 1.xlsx`
*   **Size:** 2000 rows, 17 columns
*   **Features:** Contains a mix of numerical (`int64`, `float64`) and categorical (`object`) features.
*   **Missing Values:** No missing values were found.
*   **Target Variable:** `churn` (binary: 0 for 'No Churn', 1 for 'Churn').
*   **Key Challenge:** The dataset exhibits a significant class imbalance, with approximately 98.5% 'No Churn' and 1.5% 'Churn'.

## Tasks Performed

### 1. Dataset Understanding
*   Loaded the dataset and performed initial exploration.
*   Confirmed the number of rows and columns (2000 rows, 17 columns).
*   Identified data types for all features.
*   Verified the absence of missing values.
*   Obtained basic statistical summaries of numerical features.
*   Analyzed the distribution of the target variable, `churn`, highlighting the severe class imbalance.

### 2. Data Preprocessing
*   Dropped the `customer_id` column as it's an identifier.
*   Categorical features (`region`, `plan_type`, `contract_type`, `payment_method`) were one-hot encoded using `OneHotEncoder`.
*   Numerical features were scaled using `StandardScaler` to normalize their ranges.
*   The processed dataset was split into training (80%) and testing (20%) sets using `train_test_split` with stratification to maintain the target variable's class distribution in both sets.

### 3. Neural Network Model Building (Initial Model)
*   A feed-forward neural network was constructed using TensorFlow/Keras.
*   **Architecture:**
    *   Input layer (matching the number of features).
    *   First hidden layer: 64 neurons, ReLU activation, 0.3 dropout.
    *   Second hidden layer: 32 neurons, ReLU activation, 0.3 dropout.
    *   Output layer: 1 neuron, Sigmoid activation (for binary classification).
*   **Compilation:** Adam optimizer (learning rate 0.001), `binary_crossentropy` loss, and `accuracy` metric.

### 4. Training and Evaluation (Initial Model)
*   The initial model was trained for 50 epochs with a batch size of 32.
*   **Evaluation:** Achieved a high overall test accuracy (around 0.9850).
*   **Critical Finding:** Despite high overall accuracy, the model demonstrated severe underfitting for the minority 'churn' class, yielding 0.00 precision, recall, and F1-score for class 1. This indicated the model was defaulting to predicting 'No Churn' for almost all instances due to the overwhelming class imbalance.

### 5. Hyperparameter Experimentation
To address the poor performance on the minority class, three experiments were conducted, primarily focusing on improving `Churn_Recall`:

*   **Experiment 1 (Class Weights):**
    *   **Modification:** Introduced balanced class weights during training to penalize misclassifications of the minority class more heavily.
    *   **Result:** `Churn_Recall` significantly improved to 0.17, while `Churn_Precision` was 0.07. This was a notable improvement over the initial model but still indicated a high number of false positives.

*   **Experiment 2 (Increased Neurons + Class Weights):**
    *   **Modification:** Increased the hidden layer neurons (128 and 64 respectively) while retaining class weights.
    *   **Result:** The model's ability to predict churn did not consistently improve (`Churn_Recall` 0.00, `Churn_Precision` 0.00 in one run; `Churn_Recall` 0.17, `Churn_Precision` 0.11 in another run), suggesting that increased model capacity alone wasn't the primary solution for this imbalance.

*   **Experiment 3 (Lower Learning Rate + Class Weights):**
    *   **Modification:** Reverted to the initial architecture but reduced the learning rate of the Adam optimizer to 0.0005, combined with class weights.
    *   **Result:** Achieved the best balance among experiments, with `Churn_Recall` of 0.67 and `Churn_Precision` of 0.10. This configuration showed a strong improvement in identifying churn cases.

*   **Comparison Table:** A summary table was created to compare the key metrics (Test Accuracy, Churn Precision, Churn Recall, Churn F1-Score) across all models, illustrating the trade-offs.

### 6. Final Reflection
*   **Weights and Biases:** Explained their roles in determining connection strength and allowing activation functions to shift, respectively.
*   **Activation Functions:** Highlighted their necessity for introducing non-linearity, enabling the network to learn complex patterns.
*   **Learning Rate Impact:** Discussed how a high learning rate can cause overshooting/divergence, while a low learning rate leads to slow convergence or getting stuck in local minima.
*   **Underfitting/Overfitting:** Concluded that the initial model exhibited severe underfitting for the minority class. Class weighting effectively mitigated this, improving recall for churn. No strong signs of overfitting were observed in the experiments.
