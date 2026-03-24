# 🎵 Music Genre Recommender

A machine learning project that recommends music genres based on user age and gender using a **Decision Tree Classifier**.

---

## 📌 Overview

This project trains a Decision Tree model on music preference data to predict which genre a user is likely to enjoy. It also exports the trained model and visualizes the decision tree.

---

## 🗂️ Project Structure

```
├── Music_Model.ipynb       # Main Jupyter Notebook
├── music.csv               # Dataset (age, gender, genre)
├── music-recommender.joblib  # Saved trained model
├── music-recommender.dot   # Decision tree visualization (Graphviz)
└── README.md
```

---

## 🧠 How It Works

The model takes two input features:

| Feature  | Description                        |
|----------|------------------------------------|
| `age`    | Age of the user (integer)          |
| `gender` | Gender of the user (1 = Male, 0 = Female) |

And predicts a **music genre** such as `HipHop`, `Jazz`, `Classical`, etc.

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas scikit-learn joblib
```

### Run the Notebook

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/music-recommender.git
   cd music-recommender
   ```

2. Open the Jupyter Notebook:
   ```bash
   jupyter notebook Music_Model.ipynb
   ```

3. Run all cells to train the model, evaluate accuracy, and export the tree.

---

## 📊 Model Training & Evaluation

- **Algorithm:** Decision Tree Classifier (`sklearn`)
- **Train/Test Split:** 80% / 20%
- **Accuracy:** Up to `1.0` (100%) on test data *(may vary due to random split)*

---

## 💾 Saving & Loading the Model

The trained model is saved using `joblib`:

```python
import joblib

# Save
joblib.dump(model, 'music-recommender.joblib')

# Load & Predict
model = joblib.load('music-recommender.joblib')
predictions = model.predict(pd.DataFrame([[21, 1]], columns=['age', 'gender']))
# Output: ['HipHop']
```

---

## 🌳 Visualizing the Decision Tree

The tree is exported as a `.dot` file and can be rendered using [Graphviz](https://graphviz.org/):

```bash
dot -Tpng music-recommender.dot -o music-recommender.png
```

Or paste the `.dot` file content into [Graphviz Online](https://dreampuf.github.io/GraphvizOnline/).

---

## 📁 Dataset

The `music.csv` file should have the following structure:

```
age,gender,genre
20,1,HipHop
23,1,HipHop
25,1,HipHop
26,1,Jazz
...
```

---

## 🛠️ Tech Stack

- **Python 3**
- **Pandas** – Data manipulation
- **Scikit-learn** – ML model
- **Joblib** – Model persistence
- **Graphviz** – Tree visualization

---

