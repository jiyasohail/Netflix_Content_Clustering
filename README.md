# 🎬 Netflix Content Clustering

> An unsupervised Machine Learning project that groups Netflix titles into clusters based on their genre and description using TF-IDF and K-Means clustering.

---

## 💡 What This Project Does

Instead of manually categorizing content, this project lets the algorithm discover natural groupings in the Netflix catalog. Each title is represented as a vector of words from its genre tags and description, and K-Means finds 5 distinct clusters — revealing hidden content patterns across the library.

---

## 🔍 How It Works

**Step 1 — Load & Clean Data**
The Netflix titles dataset is loaded and missing values are handled: the `director` column is dropped, while `cast`, `country`, `date_added`, `rating`, and `duration` are filled with sensible defaults.

**Step 2 — Feature Engineering**
A combined `features` column is created by merging each title's `listed_in` (genres) and `description` fields into a single text string.

**Step 3 — TF-IDF Vectorization**
The text features are converted into numerical vectors using `TfidfVectorizer`, which weighs words by how important they are across the dataset (common words like "the" get low weight; unique descriptive words get high weight).

**Step 4 — K-Means Clustering**
K-Means groups all titles into **5 clusters** based on their TF-IDF vectors.

**Step 5 — PCA Visualization**
Since TF-IDF produces high-dimensional vectors, PCA reduces them to 2 components so the clusters can be plotted and visually inspected.

---

## 📊 Visualizations

- Scatter plot of all Netflix titles colored by cluster
- Sample titles printed from each cluster to interpret what each group represents

---

## 🛠️ Tech Stack

- **Python**
- **Pandas & NumPy** — Data loading and preprocessing
- **scikit-learn** — TF-IDF, K-Means, PCA
- **Matplotlib & Seaborn** — Cluster visualization

---

## 🗂️ Project Structure

```
├── NetflixCluster.ipynb        # Main notebook
├── netflix_titles.csv.zip      # Dataset (source: Kaggle)
└── README.md
```

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/jiyasohail/Netflix_Content_Clustering.git
cd Netflix_Content_Clustering
```

### 2. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### 3. Run the notebook

Open `NetflixCluster.ipynb` in Jupyter or Google Colab and run all cells.

---

## 💡 Key Findings

Titles cluster naturally around broad content themes — action/thriller content, family and kids shows, documentaries, international drama, and stand-up/comedy specials tend to form their own groups. Genre tags carry strong signal, but the description text helps refine boundaries between similar genres.

---

## 👩‍💼 Author

**Javariya Sohail** — Computer Science Graduate & Data Enthusiast
