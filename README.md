# Hepatitis Recommendation System

**Deployed via Microsoft Azure Machine Learning & Telegram Bot**  
*By Rahul Kumar*

---

## Table of Contents

- [Project Overview](#project-overview)
- [Motivation](#motivation)
- [Methodology](#methodology)
- [System Architecture](#system-architecture)
- [Installation & Requirements](#installation--requirements)
- [Usage](#usage)
- [Directory Structure](#directory-structure)
- [Results & Sample Output](#results--sample-output)
- [References](#references)
- [Contact](#contact)

---

## Project Overview

This project implements a Hepatitis Recommendation System using a machine learning model deployed on Microsoft Azure and accessed via a Telegram chatbot. The system collects patient information through a conversational interface and predicts the likelihood of Hepatitis, providing actionable recommendations.

---

## Motivation

Early and accurate identification of Hepatitis is critical for timely intervention and improved patient outcomes. By leveraging cloud-based ML and user-friendly chatbots, this project aims to make Hepatitis risk assessment more accessible and scalable.

---

## Methodology

1. **Model Development**  
   - Built and trained a classification model using Microsoft Azure Machine Learning Studio (classic) on a hepatitis dataset.
   - Utilized feature selection and data preprocessing modules.
   - Trained model exported as a web service for real-time inference.

2. **Recommendation System Techniques**  
   - **Content-Based Methods:** Used explicit patient features as model inputs.
   - **Model-Based Approach:** Classifier predicts Hepatitis risk based on input features.

3. **Chatbot Integration**  
   - Developed a Telegram bot using Python and the `python-telegram-bot` library.
   - The bot asks a sequence of medical questions, collects responses, and sends them to the Azure ML web service via API.
   - The bot returns the prediction and recommendations to the user in real time.

---

## System Architecture
```
User (Telegram)
│
▼
Telegram Bot (Python)
│
▼
Azure ML Web Service (Hepatitis Model)
│
▼
Prediction & Recommendation
```
---

## Installation & Requirements

**Prerequisites:**
- Python 3.7+
- `python-telegram-bot==12.0`
- `requests`, `json`, `pandas`, `sklearn`, `urllib`

**Install dependencies:**
```
pip install python-telegram-bot==12.0 requests pandas scikit-learn
```

**Clone the repository:**
```
git clone https://github.com/YourUsername/Hepatitis-Recommendation-System.git
cd Hepatitis-Recommendation-System
```

---

## Usage

1. **Configure your bot:**
   - Register a new Telegram bot via [@BotFather](https://t.me/BotFather).
   - Obtain your bot token.

2. **Configure Azure ML Web Service:**
   - Deploy your trained model as a web service on Azure ML.
   - Obtain the scoring URI and API key.

3. **Set up your credentials in the bot script:**

| Variable      | Example Value                        | Description                         |
| ------------- | ------------------------------------ | ----------------------------------- |
| `updater`     | `Updater("YOUR_TELEGRAM_BOT_TOKEN")` | Your Telegram bot token             |
| `scoring_uri` | `YOUR_AZURE_SCORING_URI`             | Azure ML web service endpoint URL   |
| `key`         | `YOUR_AZURE_API_KEY`                 | Azure ML API key for authentication |

4. **Run the bot:**

5. **Interact with your bot on Telegram:**
- Start a chat with your bot and follow the prompts.

---

## Directory Structure
```
Hepatitis-Recommendation-System/
│
├── data/             # Datasets and input files
├── hepatitis_bot.py  # Main Telegram bot script
├── model/            # Model files or Azure deployment scripts
├── requirements.txt  # Python dependencies
├── README.md         # Project documentation
└── LICENSE

```

---

## Results & Sample Output

- **Bot Interaction:**  
  The bot sequentially asks medical questions (age, gender, symptoms, etc.), collects responses, and returns a recommendation:
  - *"The patient is having Hepatitis. The patient may not live long until he changes his lifestyle."*
  - *"The patient is not having Hepatitis. The patient is free to leave the hospital."*

- **Sample Prediction:**
```json
{
"Inputs": {
"input1": {
"ColumnNames": ["Age", "Gender", "Steroids", "..."],
"Values": [[67, 1, 1, 1, 0, 1, "..."]]
}
},
"GlobalParameters": {}
}
```
---

## References

1. [Microsoft Azure Machine Learning Studio](https://studio.azureml.net/)
2. [python-telegram-bot Documentation](https://python-telegram-bot.readthedocs.io/)
3. [Telegram Bot API](https://core.telegram.org/bots/api)

---

## Contact

**Author:** Rahul Kumar  
**Email:** kumar.rahul226@gmail.com  
**LinkedIn:** [rk95-dataquasar](https://www.linkedin.com/in/rk95-dataquasar/)

---
