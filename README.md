# Disaster Response Pipeline Project

### Table of Contents

1. [Installation](#installation)
2. [Project Motivation](#motivation)
4. [Project Descriptions](#project)
3. [File Descriptions](#files)
5. [Instructions](#instructions)

## Installation <a name="installation"></a>

    All libraries are available in Anaconda distribution of Python 3.*
    Additional libraries:
        $ pip install sqlalchemy
        $ pip install nltk
        $ pip install lightgbm
        $ pip install flask
        $ pip install plotly    

## Project Motivation<a name="motivation"></a>

In this project I will use messages that were sent during disaster events and build a machine learning to identify messages or events in need of attention or relief.

## Project Descriptions<a name="project"></a>

The project has three componants which are:

1. **ETL Pipeline:** `process_data.py` file contain the script to create ETL pipline which:

    - Load and merge the `messages` and `categories` data
    - Clean the merged data
    - Store the data in a SQLite database

2. **ML Pipeline:** `train_classifier.py` file contain the script to create ML pipline which:

    - Load data from SQLite database
    - Split data into training set and test set
    - Build pipeline of text processing and machine learning
    - Training and Tuning model
    - Store the best model to a `.pkl` file

3. **Flask Web App:** the web app enables the user to enter a disaster message, and then view the categories of the message.


## File Descriptions <a name="files"></a>

The files structure is arranged as below:

	- README.md: read me file
    - \app
        - run.py: Flask code
    - \templates
        - master.html: index web page of web application 
        - go.html: result web page of web application
    - \data
        - disaster_categories.csv: categories data
        - disaster_messages.csv: messages data
        - DisasterResponse.db: disaster response database
        - process_data.py: ETL code
    - \models
        - train_classifier.py: Model code
        - classifier.pkl: Trained model

## Instructions<a name="instructions"></a>

1. Run the following commands in the project's root directory to set up your database and model.

    - To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
    - To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`

2. Run the following command in the app's directory to run your web app.
    `python run.py`

3. Go to http://0.0.0.0:3001/