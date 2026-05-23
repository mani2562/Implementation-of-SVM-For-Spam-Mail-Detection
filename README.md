# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Detect File Encoding: Use chardet to determine the dataset's encoding.
2. Load Data: Read the dataset with pandas.read_csv using the detected encoding.
3. Inspect Data: Check dataset structure with .info() and missing values with .isnull().sum().
4. Split Data: Extract text (x) and labels (y) and split into training and test sets using train_test_split.
5. Convert Text to Numerical Data: Use CountVectorizer to transform text into a sparse matrix.
6. Train SVM Model: Fit an SVC model on the training data.
7. Predict Labels: Predict test labels using the trained SVM model.
8. Evaluate Model: Calculate and display accuracy with metrics.accuracy_score.

## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: Manikandan G
RegisterNumber:  212225040224
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.svm import SVC
from sklearn.metrics import accuracy_score, classification_report, confusion_matrix

data = pd.read_csv("C:/Users/acer/Downloads/spam.csv", encoding="latin-1")
data = data[['v1', 'v2']]
data.columns = ['label', 'message']
data['label'] = data['label'].map({'ham': 0, 'spam': 1})

X = data['message']
y = data['label']

vectorizer = TfidfVectorizer(stop_words='english')
X = vectorizer.fit_transform(X)

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

model = SVC(kernel='linear')
model.fit(X_train, y_train)

y_pred = model.predict(X_test)

print("Accuracy:", accuracy_score(y_test, y_pred))
print("\nClassification Report:\n")
print(classification_report(y_test, y_pred))

cm = confusion_matrix(y_test, y_pred)
print("\nConfusion Matrix:\n")
print(cm)
*/
```

## Output:
![SVM For Spam Mail Detection](sam.png)
<img width="622" height="462" alt="Screenshot 2026-05-24 000311" src="https://github.com/user-attachments/assets/c077826a-a888-4b23-84d3-4022238242c5" />




## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
