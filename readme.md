# Disaster Response Pipeline  

This project helps classify disaster-related messages into different categories to assist emergency response teams.  

##  Project Overview  

### 1️. ETL Pipeline (`process_data.py`)  
- Cleans and processes disaster messages and categories.  
- Stores the data in an SQLite database.  

### 2️. Machine Learning Pipeline (`train_classifier.py`)  
- Trains a model to classify messages into multiple categories.  
- Uses **GridSearchCV** for optimization.  
- Saves the trained model as a `.pkl` file.  

### 3. Flask Web App (`run.py`)  
- Provides a user-friendly interface for message classification.  
- Displays classification results and dataset insights.  

---

##  Project Structure  

```bash
Disaster-Response-Pipeline/
├── app/
│   ├── templates/         # HTML pages
│   ├── run.py             # Flask app
├── data/
│   ├── disaster_messages.csv
│   ├── disaster_categories.csv
│   ├── DisasterResponse.db  # Processed database
│   ├── process_data.py      # ETL script
├── models/
│   ├── train_classifier.py  # Machine learning script
├── requirements.txt         # Dependencies
└── README.md                # Project documentation
```
## Getting Started
Running the project
### Prerequisites
- Python 3.6+
- pip (Python package manager)

### Install Dependencies
Run the following command to install required Python libraries:

```pip install -r requirements.txt```

### Download Required NLTK Data
Run the following in Python to download necessary NLTK components:

```
import nltk
nltk.download('punkt')
nltk.download('wordnet')
```
---
## Running the Project

### Process Data (ETL pipeline)
```
python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db
```

### Train Model

```
python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl
```

### Run the Web App
```
python app/run.py
```
---

## Key Features
- Multi-label classification for disaster messages.
- Optimized with GridSearchCV for better accuracy.
- NLTK-based text processing (tokenization & lemmatization).
- Interactive Flask web app with data visualizations.

## Handling Class Imbalance
To improve classification for rare categories (e.g., "missing_people"), we use:
- Class weighting in the model.
- Oversampling (SMOTE) or undersampling for better balance.
- Threshold tuning for optimizing precision vs. recall.