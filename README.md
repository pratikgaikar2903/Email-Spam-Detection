
# 📧 SMS Spam Classification using Naive Bayes

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python) 
![Pandas](https://img.shields.io/badge/pandas-FF1493?style=for-the-badge&logo=pandas&logoColor=white) 
![Numpy](https://img.shields.io/badge/numpy-013243?style=for-the-badge&logo=numpy&logoColor=white) 
![Scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white) 
![Jupyter Notebook](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

## 📋 Project Overview

This project presents an end-to-end machine learning solution for classifying SMS messages as either 'spam' or 'not spam' (ham). Leveraging a Multinomial Naive Bayes classifier, this notebook demonstrates best practices in data preprocessing, feature engineering for text data, model training, and rigorous evaluation. The primary goal is to accurately identify unsolicited and unwanted messages, enhancing user experience and security.

## ✨ Features

*   **Data Loading & Initial Inspection**: Efficiently load and inspect the dataset.
*   **Data Cleaning**: Standardize category labels for consistency.
*   **Exploratory Data Analysis (EDA)**: Understand class distribution and data characteristics.
*   **Text Preprocessing**: Convert raw text into numerical features using `CountVectorizer`.
*   **Model Building**: Implementation of a Multinomial Naive Bayes classifier, a robust choice for text classification.
*   **Model Training & Evaluation**: Train the model on prepared data and assess performance using standard metrics (Accuracy, Precision, Recall, F1-Score, Confusion Matrix).
*   **Interactive Prediction**: A simple interface to classify new, user-inputted SMS messages in real-time.

## 🛠️ Technologies Used

*   **Python**: Programming language.
*   **Pandas**: Data manipulation and analysis.
*   **NumPy**: Numerical operations.
*   **Scikit-learn**: Machine learning library (for `MultinomialNB`, `CountVectorizer`, `train_test_split`, `metrics`).
*   **Jupyter Notebook / Google Colab**: Interactive development environment.

## 📊 Dataset Information

The dataset `spam mail.csv` is a collection of SMS messages, each labeled as 'ham' (legitimate) or 'spam'. It typically contains two columns:

*   `Category`: The target variable, indicating 'ham' or 'spam'.
*   `Masseges`: The text content of the SMS.

The dataset exhibits a class imbalance, with a significantly higher number of 'ham' messages compared to 'spam' messages. This imbalance is addressed through careful model evaluation.

## ⚙️ Installation

To run this notebook, you will need a Python environment with the following libraries installed:

```bash
pip install pandas numpy scikit-learn
```

Alternatively, you can run this notebook directly in [Google Colab](https://colab.research.google.com/) as all dependencies are pre-installed or can be easily installed within the environment.

## 🚀 Usage Guide

1.  **Open the Notebook**: Access the `SMS_Spam_Classification.ipynb` notebook (this file) in Google Colab or your local Jupyter environment.
2.  **Run All Cells**: Execute all cells sequentially from top to bottom. This will perform data loading, preprocessing, model training, and evaluation.
3.  **Interactive Prediction**: The final code cell allows you to input an SMS message and get an instant spam classification result.

## 📁 Project Structure (Suggested)

For a production-ready project, the following structure is recommended:

```
. (root folder)
├── SMS_Spam_Classification.ipynb  # The main project notebook
├── data/
│   └── spam mail.csv              # Raw dataset
├── models/
│   └── spam_classifier_model.pkl  # (Future) Trained model save file
├── notebooks/
│   └── experiments.ipynb          # (Future) Additional experimental notebooks
├── src/
│   ├── preprocess.py              # (Future) Data preprocessing functions
│   └── train.py                   # (Future) Model training script
├── requirements.txt               # Python dependencies
├── .gitignore                     # Files/folders to ignore in Git
└── README.md                      # Project overview (this file)
```

## 📈 Results

Our Multinomial Naive Bayes model achieved strong performance metrics on the test set:

*   **Accuracy**: 98.03%
*   **Confusion Matrix**:
    ```
    [[954  19]
     [  3 139]]
    ```
    *   True Negatives (Not Spam correctly classified): 954
    *   False Positives (Not Spam misclassified as Spam): 19
    *   False Negatives (Spam misclassified as Not Spam): 3
    *   True Positives (Spam correctly classified): 139

*   **Classification Report**:
    ```
                  precision    recall  f1-score   support

        Not Spam       1.00      0.98      0.99       973
            spam       0.88      0.98      0.93       142

        accuracy                           0.98      1115
       macro avg       0.94      0.98      0.96      1115
    weighted avg       0.98      0.98      0.98      1115
    ```

**Key Observations**:
*   The model demonstrates excellent overall accuracy. 
*   It has very high precision for 'Not Spam' (1.00), meaning very few legitimate messages are falsely flagged as spam.
*   The recall for 'spam' is also very high (0.98), indicating that the model successfully identifies most of the actual spam messages.
*   The low number of false negatives (3) is crucial for a spam detector, as letting spam through is often more detrimental than occasionally flagging a legitimate message (false positive).

## ✅ Conclusion

This project successfully developed and evaluated an SMS spam classification model using a Multinomial Naive Bayes algorithm. We achieved a high accuracy of 98.03% and robust performance across precision, recall, and F1-score, particularly for the critical 'spam' class. The project demonstrates a complete workflow from raw data to an interactive prediction system. While the class imbalance presented a challenge, the chosen model and evaluation metrics effectively highlighted its strong capability in detecting spam.

## 🔮 Future Improvements

To further enhance this project, consider the following:

*   **Hyperparameter Tuning**: Optimize `CountVectorizer` and `MultinomialNB` parameters for even better performance.
*   **Advanced Text Preprocessing**: Implement stemming, lemmatization, stop-word removal, and more sophisticated tokenization.
*   **Alternative Feature Engineering**: Explore TF-IDF (Term Frequency-Inverse Document Frequency) for weighting word importance.
*   **More Complex Models**: Experiment with Transformer-based models (e.g., BERT, RoBERTa) or ensemble methods for potentially higher accuracy, though at the cost of increased computational resources.
*   **Larger/More Diverse Datasets**: Training on a broader range of SMS messages could improve generalization.
*   **Model Deployment**: Integrate the trained model into a web application (e.g., using Flask/Django) or a mobile application for real-time prediction in a production environment.
*   **Explainable AI (XAI)**: Implement techniques to understand *why* the model makes certain predictions.

## ✍️ Author

*   **[Your Name/Alias]** - [Link to your GitHub/LinkedIn]

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
