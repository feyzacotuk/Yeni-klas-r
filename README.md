# Disaster Response Pipeline Project

## Table of Contents
- [Project Overview](#project-overview)
- [Components](#components)
  - [ETL Pipeline](#etl-pipeline)
  - [ML Pipeline](#ml-pipeline)
  - [Flask Web App](#flask-web-app)
- [Setup Instructions](#setup-instructions)
- [File Descriptions](#file-descriptions)
- [Acknowledgements](#acknowledgements)

## Project Overview
This project aims to build a web app that classifies disaster response messages. The app uses a machine learning pipeline to categorize messages so that they can be sent to the appropriate disaster response agency.

## Components
The project consists of three main components:

### ETL Pipeline
A data cleaning pipeline that:
- Loads the messages and categories datasets
- Merges the two datasets
- Cleans the data
- Stores it in a SQLite database

### ML Pipeline
A machine learning pipeline that:
- Loads data from the SQLite database
- Splits the dataset into training and test sets
- Builds a text processing and machine learning pipeline
- Trains and tunes a model using GridSearchCV
- Outputs results on the test set
- Exports the final model as a pickle file

### Flask Web App
A web application that:
- Loads the model and data from the database
- Provides an interface for users to input new messages
- Classifies the messages and displays the results
- Includes data visualizations using Plotly

## Setup Instructions

### Prerequisites
- Python 3.6+
- Libraries: pandas, numpy, sqlalchemy, nltk, scikit-learn, Flask, Plotly, pickle
- SQLite

### Installation
1. Clone the repository:
   ```sh
   git clone https://github.com/your_username/your_repository.git
   cd your_repository
Install the required libraries:

sh
Copy code
pip install -r requirements.txt
Download NLTK data:

sh
Copy code
python -m nltk.downloader punkt stopwords wordnet
Running the Pipelines
ETL Pipeline:
sh
Copy code
python process_data.py disaster_messages.csv disaster_categories.csv DisasterResponse.db
ML Pipeline:
sh
Copy code
python train_classifier.py DisasterResponse.db classifier.pkl
Running the Web App
Run the Flask app:

sh
Copy code
python run.py
Open the app in your browser:
Navigate to http://localhost:3001/

File Descriptions
process_data.py: Script to process and clean the data.
train_classifier.py: Script to train the machine learning model.
run.py: Flask application.
DisasterResponse.db: SQLite database containing the cleaned data.
classifier.pkl: Trained machine learning model.
data: Folder containing the raw datasets.
app: Folder containing the web app templates and static files.
Acknowledgements
This project is part of the Udacity Data Scientist Nanodegree. The datasets used in this project are provided by Figure Eight.