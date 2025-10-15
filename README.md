
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

We started by pre-processing the Spotify dataset to prepare it for analysis and modeling. Key features like danceability, energy, loudness, and tempo were selected as predictors, with track_popularity as the target variable. To ensure data quality, missing values were handled by removing incomplete records. The dataset was then split into training (80%) and testing (20%) subsets to train and evaluate the model's performance. Numerical features were standardized using StandardScaler, which normalized the data to have a mean of 0 and a standard deviation of 1. This step ensured that all features were on the same scale so one feature wasn’t overshadowing another. The processed data was then organized into structured variables (X_train, X_test, y_train, y_test) for efficient use in modeling.


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
    
<img width="1003" height="448" alt="Screenshot 2025-10-15 170731" src="https://github.com/user-attachments/assets/949663df-2575-4282-adb8-966d4d953834" />



### Random Forest Regression

###  Model Implementation
Following our baseline Linear Regression model, we implemented a **Random Forest Regression** to better capture complex patterns in predicting song popularity. This ensemble method offers several advantages for our use case:

- **Handles Non-Linear Relationships**: Effectively captures complex feature interactions
- **Robust to Outliers**: Less sensitive to extreme values that survived preprocessing
- **Reduces Overfitting**: Multiple decision trees with averaging prevent overfitting

###  Model Configuration
- **Estimators**: 100 decision trees
- **Methodology**: Each tree makes independent predictions, with final output averaged across all trees
- **Objective**: Highlight complex, non-linear relationships in the audio feature data

###  Performance Metrics
| Metric | Score | Improvement vs Linear Regression |
|--------|-------|----------------------------------|
| **MSE** | 474.22 | ↓ 116.79 |
| **RMSE** | 21.78 | ↓ 2.53 |
| **MAE** | 17.05 | ↓ 5.27 |
| **R² Score** | 0.23 | ↑ 0.193 |

**Interpretation**: The model showed moderate improvement over Linear Regression, but still only explains **23% of the variance** in song popularity, indicating significant room for improvement.

###  Feature Importance Analysis
One of Random Forest's key advantages is providing clear feature importance metrics:

| Feature | Importance | Interpretation |
|---------|------------|----------------|
| **Tempo** | 28.84% | Most influential - song speed (BPM) plays notable role in listener appeal |
| **Loudness** | 26.47% | Second most important - volume intensity significantly impacts popularity |
| **Energy** | 23.67% | Moderate influence - track intensity affects listener preference |
| **Danceability** | 23.02% | Notable contributor - rhythm and dance appeal matters for popularity |

###  Key Insights
- **Balanced Feature Impact**: All four features show similar importance levels (20-30% range)
- **No Dominant Predictor**: No single audio feature overwhelmingly drives popularity predictions
- **Moderate Explanatory Power**: Combined features explain limited variance, suggesting missing critical factors
- **Model Advancement**: Random Forest outperformed Linear Regression but still fell short of robust predictive capability

> **Conclusion**: While Random Forest provided better performance and valuable feature insights, the limited R² score underscores the complexity of predicting musical popularity and the need for additional features beyond basic audio characteristics.

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
## 📖 Storytelling & Conclusion

###  Key Insights
- **Positive Influencers**: Loudness and danceability consistently emerged as positive contributors to song popularity
- **Unexpected Finding**: Energy showed a negative correlation with popularity, challenging conventional assumptions
- **Feature Limitations**: Audio characteristics alone proved insufficient for highly accurate popularity predictions

###  Industry Implications
The project reveals the evolving relationship between creativity and data in the music industry:

- **Production Guidance**: Insights on danceability and loudness can inform artist development
- **Marketing Optimization**: Data-driven approaches can enhance playlist curation and promotional strategies
- **Strategic Planning**: Stakeholders can leverage these findings for more targeted content creation

###  Challenges & Limitations
- **Model Performance**: Low R² scores across all models indicate significant unexplained variance
- **Data Complexity**: Musical preference involves subjective factors beyond measurable audio features
- **Predictive Gaps**: Current features capture only a portion of what makes songs popular

###  Technical Learnings
- **Feature Selection**: Critical importance of choosing relevant predictors for model success
- **Data Quality**: Essential role of preprocessing and standardization in model performance
- **Model Evaluation**: Need for comprehensive metrics beyond basic accuracy measures

###  Future Improvements
- **Enhanced Metadata**: Incorporate genre, release timing, and social media trends
- **Advanced Feature Engineering**: Develop more nuanced audio and contextual features
- **Model Innovation**: Explore ensemble methods and deep learning approaches
- **Domain Integration**: Combine machine learning with music industry expertise

###  Personal & Professional Growth
This project reinforced essential data science principles:
- **Systematic Problem-Solving**: From data cleaning to model interpretation
- **Critical Thinking**: Balancing technical rigor with creative solution-finding
- **Effective Communication**: Translating complex results into actionable business insights
- **Real-World Application**: Bridging theoretical knowledge with practical industry challenges

> **Final Takeaway**: While audio features provide valuable insights, predicting song popularity requires a more holistic approach that combines technical data analysis with deep understanding of musical artistry and cultural trends.












---

## 🔗 References
- Yadav, Amit. ["Linear Regression vs Random Forest"](https://medium.com/@amit25173/linear-regression-vs-random-forest-7288522be3aa) - Medium, 20 July 2024
- Spotify Web API Documentation
- Scikit-learn, XGBoost Documentation

---

<div align="center">

**🎧 Where Data Meets the Beat 🎶**

</div>






