# Sleep Score Calculator and Mental Health Predictor

This project is a simple Python-based application that contains two parts:

* Sleep Score Calculator
* Mental Health Score Predictor

## Sleep Score Calculator

The Sleep Score Calculator calculates a score out of 100 using:

* Number of hours slept
* Sleep quality rating

### Formula

**Sleep Score = Sleep Duration Score + (Sleep Quality × 8)**

The sleep duration score is calculated as:

* 7–9 hours → 60 points
* 6–7 hours or 9–10 hours → 45 points
* Less than 6 hours or more than 10 hours → 30 points

The sleep quality is given as a rating from 1 to 5.

The final score is limited to a maximum of 100.

## Mental Health Predictor

The Mental Health Predictor uses a Machine Learning model to predict whether a student may have depression based on information from the dataset.

A **Decision Tree Classifier** is used for prediction.

The model is trained using the following dataset:

**Depression Student Dataset.csv**

The dataset contains student-related information such as:

* Gender
* Age
* Academic Pressure
* Study Satisfaction
* Sleep Duration
* Dietary Habits
* Suicidal Thoughts
* Study Hours
* Financial Stress
* Family History of Mental Illness
* Depression

The `Depression` column is used as the target variable.

## Technologies Used

* Python
* Pandas
* Scikit-learn
* Decision Tree Classifier

## Dataset

The project uses the **Depression Student Dataset**.

The dataset is stored as:

```text
Depression Student Dataset.csv
```

## How to Run

1. Download or clone the project.
2. Keep `Depression Student Dataset.csv` in the same folder as the Python file.
3. Install the required libraries:

```bash
pip install pandas scikit-learn
```

4. Run the Python program.

The program will first calculate the sleep score and then use the trained Machine Learning model to make the mental health prediction.

## Example Output

```text
Model Accuracy: 85.15 %

Sleep Score Calculator

How many hours do you sleep? 7
Sleep quality (1-5): 4

Sleep Score: 92 / 100

Mental Health Predictor

Age: 23
Academic pressure (1-5): 4
Study satisfaction (1-5): 2
Financial stress (1-5): 3
Suicidal thoughts? (Yes/No): No

Mental Health Prediction: No Depression
```

## Purpose

The purpose of this project is to demonstrate basic Python programming, data processing, and Machine Learning using a real-world student dataset.

The mental health prediction is for educational purposes only and should not be considered a medical diagnosis.
