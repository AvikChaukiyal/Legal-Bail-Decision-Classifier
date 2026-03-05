Legal Bail Decision Classification
This project builds a binary text classification model to predict whether a bail petition in a legal case is Accepted or Rejected based on court case text.

The model is fine-tuned using a transformer-based architecture (Legal-BERT) on the ILDC (Indian Legal Documents Corpus) dataset.

Project Overview
Legal documents contain complex textual arguments describing case details and court reasoning. This project applies Natural Language Processing (NLP) and Transformer models to automatically classify bail decisions from such legal case descriptions.

The system learns patterns in legal text to determine whether the final bail decision was granted or denied.

Dataset
Dataset used: ILDC – Indian Legal Documents Corpus

Dataset source:
https://huggingface.co/datasets/Exploration-Lab/IL-TUR

The dataset contains Indian court case records including facts, arguments, and bail decisions.

Dataset Statistics
Split	Samples
Train	~123,742
Validation	~17,707
Test	~35,400
Each dataset entry contains:

text → legal case description

label → bail decision

Label mapping:

0 → Rejected
1 → Accepted
Model
The project uses the transformer model:

Legal-BERT

Pretrained model:

nlpaueb/legal-bert-base-uncased
Legal-BERT is trained on legal text corpora and performs well on legal NLP tasks.

Training Pipeline
The following steps are used during model training:

Load ILDC dataset from HuggingFace

Preprocess legal case text

Tokenize input text using a transformer tokenizer

Fine-tune Legal-BERT for binary classification

Evaluate model performance on validation data

Save the trained model for inference

Example Prediction
Input case text:

The appeal is allowed and the accused is acquitted.
Model prediction:

Accepted
Technologies Used
Python

PyTorch

HuggingFace Transformers

HuggingFace Datasets

Scikit-learn

Google Colab

Repository Structure
legal-bail-decision-classifier
│
├── notebooks
│   └── training.ipynb
│
├── src
│   ├── train.py
│   ├── evaluate.py
│   └── inference.py
│
├── requirements.txt
└── README.md
Installation
Clone the repository:

git clone https://github.com/AvikChaukiyal/Legal-Bail-Decision-Classifier.git
cd legal-bail-decision-classifier
Install dependencies:

pip install -r requirements.txt
Training the Model
Run the training script:

python src/train.py
Running Inference
After training the model:

python src/inference.py
Example output:

Prediction: Accepted
Future Improvements
Possible extensions for this project:

Add explainable AI (SHAP / LIME)

Deploy model using FastAPI

Build a legal case classification web app

Train larger transformer models

Improve model evaluation using additional metrics

Author
Avik Chaukiyal
GitHub: https://github.com/AvikChaukiyal