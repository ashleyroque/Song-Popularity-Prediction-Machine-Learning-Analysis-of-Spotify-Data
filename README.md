
<div align="center">
<img src="https://github.com/user-attachments/assets/f918a993-7bcf-4097-80ec-04fb52ff4f1b" width="200" alt="Spotify Logo" />
</div>

# Song Popularity Prediction: Machine Learning Analysis of Spotify Data 
**By:**  Ashley Roque Gutierrez, Isabella Kleckner, Cate Slaven, Divya Shah, and Emilia Olivera


## 📜 Project Overview
This project seeks to identify the relationship between song characteristics and metadata to develop a regression model that predicts a song's popularity. Using a dataset of 30,000 Spotify songs, we analyze features such as genre, danceability, energy, loudness, and tempo. The goal is to provide stakeholders in the music industry with data-driven insights to inform production and marketing decisions in a highly competitive market.


## 📌 Impact 
This project highlights the potential to enhance audience engagement and market success in the music industry by bridging the gap between art and data.

- **Data-Driven Insights**: Helps stakeholders understand success-driving characteristics like genre, danceability, and production quality.
- **Artist Support**: Provides beginner artists with actionable insights to refine their work.
- **Marketing Optimization**: Enhances playlist creation and promotional strategies.
- **Industry Advancement**: Combines creativity with analytics to reveal cross-genre trends and target diverse audiences.

---

## 📊 Dataset Description
This project utilizes a collection of nearly **30,000 songs** sourced from the Spotify API, obtained from [Kaggle](https://www.kaggle.com/datasets/joebeachcapital/30000-spotify-songs).

###  Track Information
- **track_id**: Unique identifier for each song
- **track_name**: Name of the song
- **track_artist**: Artist or group that performed the song
- **track_popularity**: Popularity score (0-100), with higher values indicating greater popularity
- **track_album_id**: Unique identifier for the album
- **track_album_name**: Name of the album containing the song
- **track_album_release_date**: Album release date

###  Playlist Metadata
- **playlist_name**: Name of the playlist containing the song
- **playlist_id**: Unique identifier for the playlist
- **playlist_genre**: Genre classification of the playlist
- **playlist_subgenre**: Subgenre classification of the playlist

###  Audio Features

| Feature | Range | Description |
|---------|-------|-------------|
| **danceability** | 0.0-1.0 | How suitable a track is for dancing based on tempo and rhythm stability |
| **energy** | 0.0-1.0 | Intensity and activity level (fast/loud vs. subdued) |
| **key** | 0-11 | Musical key using Pitch Class notation (0=C, 1=C♯/D♭, etc.) |
| **loudness** | -60 to 0 dB | Overall loudness averaged across the track |
| **mode** | 0 or 1 | Modality (1=major, 0=minor) |
| **speechiness** | 0.0-1.0 | Presence of spoken words vs. sung content |
| **acousticness** | 0.0-1.0 | Confidence measure of track being acoustic |
| **instrumentalness** | 0.0-1.0 | Likelihood of no vocal content (1.0=high confidence instrumental) |
| **liveness** | 0.0-1.0 | Probability of live performance audience presence |
| **valence** | 0.0-1.0 | Musical positiveness (higher values=more positive emotions) |
| **tempo** | BPM | Estimated speed of the music in beats per minute |
| **duration_ms** | milliseconds | Duration of the song |

**Target Variable**: `track_popularity` - Used as the primary metric for regression analysis predicting song success.

---

## ⚙️ Methodology

### Data Preprocessing
- **Handled Missing Values**: Removed incomplete records
- **Train-Test Split**: 80% training, 20% testing
- **Feature Scaling**: Standardized numerical features using `StandardScaler`
- **Feature Selection**: Focused on `danceability`, `energy`, `loudness`, and `tempo` as predictors for `track_popularity`

### Models Implemented
- Linear Regression (Baseline)
- Random Forest Regression
- XGBoost Regression

---

## 📈 Model Analysis & Results

### Linear Regression
- **MSE**: 591.01 | **RMSE**: 24.31 | **MAE**: 22.32 | **R²**: 0.037
- **Key Insights**:
  - Loudness and danceability were positive predictors
  - Energy showed a negative correlation with popularity
  - Model explained only 3.7% of variance in popularity



### Random Forest Regression
- **MSE**: 474.22 | **RMSE**: 21.78 | **MAE**: 17.05 | **R²**: 0.23
- **Feature Importance**:
  - Tempo (28.84%)
  - Loudness (26.47%)
  - Energy (23.67%)
  - Danceability (23.02%)
  <img width="1107" height="446" alt="Screenshot 2025-10-15 170554" src="https://github.com/user-attachments/assets/40cc771e-7e4a-4d19-acee-d3b56332f228" />


### XGBoost Regression
- **MSE**: 550.22 | **R²**: 0.104
- **Feature Importance (F-Score)**:
  - Tempo: 1445
  - Danceability: 1393
  - Energy: 1384
  - Loudness: 1366
<img width="468" height="372" alt="Screenshot 2025-10-15 170753" src="https://github.com/user-attachments/assets/32dd928a-8ab2-48fd-9099-edd53598e614" />

---

## 🧠 Storytelling & Conclusion

### Key Findings
- **Loudness** and **danceability** consistently emerged as positive contributors to song popularity
- **Energy** showed an unexpected negative correlation across models
- **Tempo** was identified as the most important feature in tree-based models

### Challenges & Limitations
- All models achieved low R² scores, indicating that audio features alone explain limited variance in popularity
- The complex, subjective nature of musical preference requires more nuanced features beyond basic audio characteristics

### Business Implications
- Provides preliminary insights for artists and producers about feature prioritization
- Highlights the need for incorporating additional factors (e.g., social media trends, cultural context)
- Demonstrates the potential of data-driven approaches in creative industries

### Future Work
- Incorporate additional metadata (genre, release date, artist popularity)
- Experiment with advanced feature engineering and deep learning models
- Combine machine learning with domain expertise for better contextualization

---

## 🔗 References
- Yadav, Amit. ["Linear Regression vs Random Forest"](https://medium.com/@amit25173/linear-regression-vs-random-forest-7288522be3aa) - Medium, 20 July 2024
- Spotify Web API Documentation
- Scikit-learn, XGBoost Documentation

---

<div align="center">

**🎧 Where Data Meets the Beat 🎶**

</div>






