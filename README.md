# 🎬 Movie Recommendation System

A dual-strategy movie recommender built with Python and scikit-learn, implementing both **Content-Based Filtering** and **User-Based Collaborative Filtering** from scratch — no heavy ML frameworks required.

---

## 📁 Project Structure

```
movie-recommender/
├── data/                        # Dataset files (not tracked in git)
│   ├── movies_metadata.csv      # Movie metadata (title, genres, cast, etc.)
│   └── ratings_small.csv        # User ratings (userId, movieId, rating)
├── notebooks/
│   └── analysis.ipynb           # EDA + recommendation demos with charts
├── src/
│   ├── content_based.py         # TF-IDF + cosine similarity recommender
│   ├── collaborative.py         # User-based collaborative filtering
│   └── app.py                   # CLI interface for both strategies
├── outputs/                     # Generated charts (auto-created)
├── requirements.txt
└── README.md
```

---

## 🧠 How It Works

### Strategy 1 — Content-Based Filtering
Builds a TF-IDF vector from each movie's metadata (genres, keywords, cast, director, overview) and uses cosine similarity to find movies with the most similar profiles.

```
Movie A metadata → TF-IDF vector → cosine similarity → Top-N similar movies
```

### Strategy 2 — Collaborative Filtering
Constructs a user-item rating matrix, computes cosine similarity between users, then recommends movies liked by similar users that the target user hasn't seen.

```
User ratings → User-item matrix → Similar users → Weighted recommendations
```

---

## 🚀 Getting Started

### 1. Clone & install
```bash
git clone https://github.com/your-username/movie-recommender.git
cd movie-recommender
pip install -r requirements.txt
```

### 2. Download dataset
Use the [TMDB Movie Metadata dataset from Kaggle](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata):
- Place `movies_metadata.csv` in `data/`
- Place `ratings_small.csv` in `data/`

### 3. Run the CLI app

**Content-based recommendations:**
```bash
cd src
python app.py --mode content --title "Inception" --top_n 10
```

**Collaborative filtering recommendations:**
```bash
python app.py --mode collaborative --user 42 --top_n 10
```

### 4. Explore the notebook
```bash
cd notebooks
jupyter notebook analysis.ipynb
```

---

## 📊 Example Output

**Content-Based — Movies similar to "The Dark Knight":**

| # | Title | Genres | Similarity Score |
|---|-------|--------|-----------------|
| 1 | Batman Begins | Action, Crime | 0.8912 |
| 2 | The Dark Knight Rises | Action, Crime | 0.8744 |
| 3 | Iron Man | Action, Sci-Fi | 0.7231 |

---

## 🔬 Techniques Used

| Concept | Where Used |
|---|---|
| TF-IDF Vectorization | Content-based feature extraction |
| Cosine Similarity | Both strategies |
| User-Item Matrix | Collaborative filtering |
| Weighted Average | Collaborative score computation |
| Pandas pivot_table | Rating matrix construction |

---

## 🛠 Tech Stack

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.4-orange?logo=scikit-learn)
![Pandas](https://img.shields.io/badge/Pandas-2.2-150458?logo=pandas)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter)

---

## 📈 Future Improvements

- [ ] Add matrix factorization (SVD) for better collaborative filtering
- [ ] Build a Streamlit web interface
- [ ] Add RMSE/MAE evaluation metrics for collaborative model
- [ ] Implement hybrid recommender combining both strategies

---

## 📝 License

MIT License — feel free to use and build on this.
