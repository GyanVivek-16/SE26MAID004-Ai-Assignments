# AQI Simple Reflex Agent

## 📌 Description

This project implements a **Simple Reflex Agent** in Python to determine the air quality condition of a given place based on its **AQI (Air Quality Index) value**.

The program takes a place name from the user, searches for that place in the AQI dataset, retrieves its AQI value and state, and then uses simple **if-else rules** to determine the air quality condition.

## ⚙️ How It Works

1. The program loads the `aqi.csv` dataset using Pandas.
2. The user enters the name of a place.
3. The program searches for the place in the dataset.
4. If the place is not found, it displays a message.
5. If the place is found, the program retrieves:

   * Place
   * State
   * AQI value
6. The AQI value is passed through a set of predefined if-else conditions.
7. The agent displays the corresponding air quality condition and status.

## 🧠 AQI Rules

| AQI Range | Condition    | Status                  |
| --------- | ------------ | ----------------------- |
| 0–50      | Good         | Air quality is good     |
| 51–100    | Satisfactory | Air quality is good     |
| 101–200   | Moderate     | Air quality is not good |
| 201–300   | Poor         | Air quality is not good |
| 301–400   | Very Poor    | Air quality is not good |
| Above 400 | Severe       | Air quality is not good |

These conditions are implemented directly using `if`, `elif`, and `else` statements in the program.

## 🛠️ Technologies Used

* Python
* Pandas
* Google Colab / Jupyter Notebook
* CSV Dataset

## 📂 Files

```text
AQI-Simple-Reflex-Agent/
│
├── AQI_Simple_Reflex_Agent.ipynb
├── aqi.csv
└── README.md
```

## ▶️ Example

```text
Enter the place: varanasi

--- AQI SIMPLE REFLEX AGENT ---
Place: Varanasi
State: Uttar Pradesh
AQI: 57
Condition: Satisfactory
Status: Air quality is good
```

The example above shows the agent taking **Varanasi** as input, finding its AQI value of **57**, and classifying it as **Satisfactory**.
