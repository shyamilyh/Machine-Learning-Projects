# 🎧 Spotify Music Recommendation System — Content-Based

### 📘 Overview
This project builds a **content‑based music recommendation system** for Spotify that suggests tracks similar to a given song by comparing audio and metadata features. The system is designed to improve music discovery by recommending songs that match a listener's taste based on *track audio features* and *genre information* rather than popularity alone.

---

## ⚙️ Project Workflow (what we did)

1. **Data Loading & Initial Inspection**
   - Loaded the dataset (`spotify.csv`) using **pandas**.
   - Displayed the top rows and verified dimensions and column types to understand the data layout.

2. **Data Cleaning**
   - Dropped rows missing critical textual identifiers (`artists`, `album_name`, `track_name`).
   - Removed duplicate tracks using `track_id` to ensure unique items in the catalog.

3. **Feature Selection**
   - Identified **numerical audio features** used for similarity calculation:
     - `popularity`, `duration_ms`, `danceability`, `energy`, `key`, `loudness`,
       `mode`, `speechiness`, `acousticness`, `instrumentalness`, `liveness`,
       `valence`, `tempo`, `time_signature`
   - Identified categorical feature:
     - `track_genre` (one‑hot encoded later)

4. **Preprocessing & Feature Engineering**
   - **Scaled numerical features** using `StandardScaler` (from scikit‑learn) so each audio attribute contributes comparably to similarity computations.
   - **One‑hot encoded** the `track_genre` column using `pd.get_dummies()` so genre information is included in the content representation.
   - Constructed a unified **content feature matrix** by combining scaled numerical features and encoded genre columns.

5. **Similarity Model (Content-Based)**
   - Computed **cosine similarity** between tracks using `sklearn.metrics.pairwise.cosine_similarity` on the content feature matrix.
   - Implemented a helper function (`get_recommendations`) that:
     - Accepts a track name (string) and returns the top‑N most similar tracks based on cosine similarity.
     - Filters and returns track metadata (artist, album, selected features) for interpretability.

6. **Qualitative Evaluation**
   - Performed **qualitative checks** using example input tracks (e.g., *“Bohemian Rhapsody”* and an acoustic/low‑energy example).
   - Inspected recommended tracks' audio features (energy, acousticness, tempo, etc.) and genres to verify they *sound* and *feel* similar to the input track.
   - Reported observations about the similarity of recommendations (e.g., similar energy/acousticness or shared genre).

---

## 📊 Key Findings 

- The content‑based approach effectively recommends songs that are **similar in audio profile and genre** to the input track — not just the most popular songs.
- Recommended songs tend to share meaningful audio characteristics such as **energy**, **acousticness**, **tempo**, and **danceability**, which aligns with human perception of musical similarity.
- Encoding genre alongside audio features helps the system prefer songs from the same or related genres when audio features alone would be ambiguous.
- Qualitative examples (inspected in the notebook) show the system returns **cohesive recommendations**: acoustic songs recommended acoustic peers, high‑energy rock tracks recommended other high‑energy rock tracks, etc.
- The notebook does not show a quantitative offline evaluation (no precision/recall or user study), so conclusions are based on qualitative inspection and feature comparisons.

---

## 🧠 Insights & Practical Notes

- **When to use content‑based:** works best when you want recommendations that respect *a listener's specific taste* (e.g., a particular vocal style, tempo, or instrumentation) and when user history is sparse or unavailable.
- **Limitations:** content‑based recommends items similar to the seed track — it cannot introduce serendipitous, diverse suggestions the way collaborative methods can. Also, performance depends on the quality and completeness of track features and genre labels.
- **Next steps (recommended):**
  - Add **textual metadata embedding** (lyrics, tags, or descriptions) using NLP to capture semantic similarity beyond acoustic features.
  - Combine content‑based results with **collaborative filtering** (hybrid system) to capture both user taste and community trends.
  - Build a small **user study** or offline metrics (e.g., held‑out playlist continuation) to quantify recommendation quality.

---

## 🧰 Tech Stack (as used in the notebook)

- Python (pandas, numpy)
- scikit‑learn (`StandardScaler`, `cosine_similarity`)
- Jupyter Notebook (analysis & qualitative evaluation)

---

## ✅ Conclusion

The notebook implements a **clean, interpretable content‑based recommender** using scaled audio features and genre encoding. Based on qualitative checks, it provides sensible similar‑track recommendations that align with human judgments of musical similarity. For production readiness, consider adding quantitative evaluation, richer metadata (lyrics, user interactions), and/or a hybrid model to improve diversity and long‑term user satisfaction.

---

