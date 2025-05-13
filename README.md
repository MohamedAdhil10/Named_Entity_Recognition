# 🧠 Named Entity Recognition (NER) using BiLSTM-LSTM

This project demonstrates how to build a Named Entity Recognition (NER) model using a BiLSTM followed by an LSTM architecture. It uses a pre-labeled dataset (`ner_dataset.csv`) and is implemented in TensorFlow/Keras, with visualization support from spaCy.

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Model Architecture](#-model-architecture)
- [Setup Instructions](#-setup-instructions)
- [Training Results](#-training-results)
- [Project Structure](#-project-structure)
- [Screenshots](#-screenshots)
- [Limitations](#-limitations)
- [Future Work](#-future-work)
- [License](#-license)

---

## 🧾 Overview

Named Entity Recognition is the task of locating and classifying named entities in text into predefined categories such as person names, organizations, locations, etc.

This project:
- Loads and processes token-tag annotated data.
- Uses token-to-index and tag-to-index mappings.
- Pads sequences and one-hot encodes tags.
- Trains a deep BiLSTM → LSTM model using Keras.
- Evaluates the model performance using `classification_report`.
- Visualizes entity recognition using spaCy's built-in NER display.

---

## 🏗️ Model Architecture

```
Embedding Layer
↓
Bidirectional LSTM (return_sequences=True)
↓
LSTM (return_sequences=True)
↓
TimeDistributed Dense Layer with softmax
```

- Loss: Categorical Crossentropy  
- Optimizer: Adam  
- Metrics: Accuracy

---

## ⚙️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/MohamedAdhil10/NER_BiLSTM_LSTM.git
cd NER_BiLSTM_LSTM
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
python -m spacy download en_core_web_sm
```

### 3. Run the Notebook

Open and run each cell of `NER_BiLSTM_LSTM.ipynb` to train and evaluate the model.

---

## 📈 Training Results

- Epochs: 25  
- Batch Size: 1000  
- Training loss decreases steadily over time (see screenshot below).
- Final evaluation on test data is shown using `classification_report`.

---

## Project Structure

```
.
├── ner_dataset.csv # Input dataset with words, POS tags, entity labels
├── ner_bilstm_lstm_model.h5 # (Not included – exceeds GitHub's file size limit)
├── NER_BiLSTM_LSTM.ipynb # Full training & evaluation code
└── README.md # Project documentation                  
```

---

## 📸 Screenshots

### 📉 Training Loss Over Epochs

![Training over loss epoch](https://github.com/user-attachments/assets/2edd8470-fedd-48e8-a124-8e29b9b9c0a0)


### 🧾 spaCy NER Visualization

![NER_Output](https://github.com/user-attachments/assets/c02e6992-e6ba-4005-bb2d-1a7bd91d534a)


---

## ⚠️ Limitations

- The trained model (`.h5`) is not included due to GitHub's 25MB upload limit.  
  **Size**: `27MB`  
  You can retrain the model using the provided notebook.

---

## 🚀 Future Work

- Integrate CRF (Conditional Random Fields) layer for better sequence prediction.
- Use a pre-trained transformer like BERT for better contextual embeddings.
- Deploy the model using Streamlit or Flask.

---

## 📄 License

This project is licensed under the MIT License.
