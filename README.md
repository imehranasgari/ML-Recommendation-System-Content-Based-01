# 🎯 Movie Recommendation System – Content-Based Filtering

## 1. Problem Statement and Goal of Project

The objective of this project is to implement a **content-based recommendation system** for movies.
Instead of relying on other users’ preferences, this method recommends movies based on their similarity to those the user has already liked — using movie metadata such as genres.

---

## 2. Solution Approach


1. **Data Preparation**

   * Load `movies.csv` (movieId, title, genres) and `ratings_sample.csv` (userId, movieId, rating, timestamp).
   * Extract release year from movie titles and clean titles.
   * Split genre strings into lists of individual genres.

2. **Feature Engineering**

   * Create a one-hot encoded matrix for genres (`movie_with_genres`) where each genre is a binary column.
   * Merge user’s rated movies with genre data.

3. **User Profile Creation**

   * For a given target user, weight each genre by the rating they assigned to the movies.
   * Build a **user profile vector** representing their genre preferences.

4. **Recommendation Scoring**

   * Compute a weighted average score for each movie by multiplying genre vectors with the user profile.
   * Rank movies in descending order of score.

5. **Output**

   * Display top recommendations for the user, excluding movies they have already rated.

---

## 3. Technologies & Libraries

* **Python**
* **pandas** – Data manipulation and merging datasets
* **NumPy** – Numerical computations for profile and similarity
* **Matplotlib** – Visualization (inline in Jupyter)
* **math.sqrt** – Imported but not the core metric in this implementation

---

## 4. Description about Dataset

* **movies.csv** – Metadata for movies (`movieId`, `title`, `genres`).
* **ratings\_sample.csv** – User ratings with (`userId`, `movieId`, `rating`, `timestamp`).
* Genres are multi-valued, separated by `|`, and expanded into binary features for model use.

---

## 5. Installation & Execution Guide

1. **Clone the repository**:

   ```bash
   git clone <repo-url>
   cd <repo-folder>
   ```
2. **Install dependencies**:

   ```bash
   pip install pandas numpy matplotlib
   ```
3. **Run the notebook**:

   ```bash
   jupyter notebook RecSys-Content-Based-movies.ipynb
   ```

---

## 6. Key Results / Performance

* Successfully generates personalized movie recommendations using only **content similarity**.
* The approach adapts to each user’s unique genre preferences without requiring other users’ ratings.

---

## 7. Screenshots / Sample Outputs

Typical outputs include:

* One-hot encoded genre matrix for all movies.
* Weighted user profile vector across genres.
* Ranked movie list based on weighted scores.

---

## 8. Additional Learnings / Reflections

* Demonstrates **content-based recommendation** logic from scratch.
* Highlights the power of metadata-driven recommendations, especially when collaborative data is sparse.
* Implementation avoids reliance on specialized recommender system libraries, showing full control over feature engineering and scoring.

---

## 👤 Author

**Mehran Asgari**
📧 [imehranasgari@gmail.com](mailto:imehranasgari@gmail.com)
🌐 [https://github.com/imehranasgari](https://github.com/imehranasgari)

---

## 📄 License

This project is licensed under the Apache 2.0 License – see the `LICENSE` file for details.

---

> 💡 *Some interactive outputs (e.g., plots, widgets) may not display correctly on GitHub. If so, please view this notebook via [nbviewer.org](https://nbviewer.org) for full rendering.*

