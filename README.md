# En-Hi Trans: English-to-Hindi Neural Machine Translation

This repository contains a Neural Machine Translation (NMT) pipeline that translates English sentences into Hindi using Hugging Face's `transformers`. The model leverages the **Helsinki-NLP/Opus-MT** architecture and is trained on the **IIT Bombay English-Hindi dataset**.

---

## 🚀 Features

- Transformer-based English-to-Hindi translation
- Utilizes Hugging Face `transformers` and `datasets` libraries
- Preprocessing and tokenization for sequence-to-sequence tasks
- Training and evaluation pipeline for NMT models
- Generates translations using `TFAutoModelForSeq2SeqLM`

---

## 📂 Project Structure

En_Hi_trans.ipynb # Jupyter Notebook containing code for training and inference
README.md # Project documentation

---

## ⚙️ Installation

Install the required dependencies:

```bash
pip install transformers datasets tensorflow
📊 Dataset
This project uses the IIT Bombay English-Hindi dataset:
Source: Hugging Face Datasets
Parallel corpus for training English ↔ Hindi translations
🖥️ Usage
Open the Jupyter Notebook:
jupyter notebook En_Hi_trans.ipynb
Run the cells to:
Load and preprocess the dataset
Train the translation model
Generate English-to-Hindi translations
📌 Example
from transformers import AutoTokenizer, TFAutoModelForSeq2SeqLM

tokenizer = AutoTokenizer.from_pretrained("Helsinki-NLP/opus-mt-en-hi")
model = TFAutoModelForSeq2SeqLM.from_pretrained("Helsinki-NLP/opus-mt-en-hi")

input_text = "I love learning machine translation."
inputs = tokenizer(input_text, return_tensors="tf")
outputs = model.generate(**inputs)
print(tokenizer.decode(outputs[0], skip_special_tokens=True))