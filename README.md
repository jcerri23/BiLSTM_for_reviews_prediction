 # 📊 Hotel Review Analysis using BiLSTM

This project is part of the final exam for the **Deep Learning** course. The goal is to analyze hotel reviews using a **Bidirectional LSTM (BiLSTM)** model to extract meaningful information from the review text. The model performs **multi-task learning**: it predicts both the **review score** (regression) and the **review sentiment** (classification into Good/Bad review).

---

## Dataset

The input dataset is `input_data.csv` and includes the following fields:

| Field                     | Type     | Description                                         |
|--------------------------|----------|-----------------------------------------------------|
| Hotel Name               | String   | Name of the hotel                                   |
| Hotel Address            | Text     | Address of the hotel                                |
| Review Date              | Date     | Date of the review (format: MM/DD/YYYY)             |
| Hotel Number Reviews     | Integer  | Total number of reviews for the hotel               |
| Reviewer Nationality     | String   | Nationality of the reviewer                         |
| Reviewer Number Reviews  | Integer  | Number of reviews submitted by the reviewer         |
| Review                   | Text     | Text of the review (max 400 words)                  |
| Review Score             | Float    | Score given to the hotel (range: 2.5 to 10)         |
| Review Type              | String   | Sentiment label of the review: Good or Bad review   |

---

##  Model Architecture

The model is based on a **Bidirectional LSTM (BiLSTM)** that processes the review text to capture both forward and backward dependencies.

### Key Components:

- **Embedding Layer**: Word-level embedding of input review text  
- **BiLSTM Layer**: To capture contextual information  
- **Dropout Layer**: For regularization  
- **Dense Layer(s)**: Fully connected layers  
- **Two Output Heads**:
  - **Review Score Prediction** (Regression Head)
  - **Sentiment Classification** (Binary Classification Head)

### Activations Used:

- **ReLU**: In hidden dense layers  
- **Sigmoid**: For binary classification output  
- **Custom Sigmoid**: Used for review score prediction (bounded regression)

---

## Objectives

- Predict the **review score** given by the reviewer (continuous value between 2.5 and 10)
- Classify the **sentiment** of the review into `Good` or `Bad`
  
---

##  Experiments & Insights

- Train a **multi-task model** using shared BiLSTM embeddings  
- Explored using an **autoencoder** to learn compressed embeddings of the review text
- Fine-tune hyperparameters 

---

