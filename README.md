# 🎶 Predicting-Spotify-Song-Popularity-A-Data-Driven-Approach 🎧
This project uses machine learning to predict Spotify song popularity based on characteristics like danceability, energy, and tempo, offering insights for data-driven decision-making in the music industry.

## 📊 Dataset

The dataset used in this project is a collection of nearly 30,000 songs sourced from the Spotify API. You can find it on [Kaggle here](https://www.kaggle.com/datasets/joebeachcapital/30000-spotify-songs). The dataset includes various features related to each song, such as track characteristics, album details, and playlist information.

### Key Features:
- **track_id**: 🎵 Unique identifier for each song.
- **track_name**: 🎤 The name of the song.
- **track_artist**: 👩‍🎤 Artist or group that performed the song.
- **track_popularity**: 🌟 Popularity score (0–100).
- **track_album_id**: 🏷 Unique identifier for the album.
- **track_album_name**: 📀 The album name.
- **track_album_release_date**: 📅 Release date of the album.
- **playlist_name**: 🎶 The name of the playlist the song is included in.
- **playlist_id**: 🔑 Unique identifier for the playlist.
- **playlist_genre**: 🎧 Genre of the playlist.
- **playlist_subgenre**: 🎶 Subgenre of the playlist.
- **danceability**: 💃 A score (0–1) indicating how suitable the track is for dancing.
- **energy**: ⚡ A measure (0–1) of the intensity and activity of the track.
- **key**: 🎼 The overall key of the track.
- **loudness**: 🔊 The loudness of the track (in decibels).
- **mode**: 🔄 Modality (major or minor).
- **speechiness**: 🗣 Presence of spoken words in the track.
- **acousticness**: 🎸 Confidence score indicating if the track is acoustic.
- **instrumentalness**: 🎹 Likelihood of being instrumental.
- **liveness**: 🎤 Presence of an audience in the recording.
- **valence**: 🌈 The musical positiveness of the track.
- **tempo**: 🕺 Tempo of the track in beats per minute (BPM).
- **duration_ms**: ⏱ Duration of the song in milliseconds.

---

## 🧑‍🔬 Methodology

The methodology for this project involves the following steps:

1. **Data Preprocessing**: 
   - Handle missing values 
   - Encode categorical features 
   - Standardize numerical variables 

2. **Feature Selection**: 
   - Use correlation analysis 🔍 to identify key features.

3. **Model Development**: 
   - Split the data into training and testing sets 
   - Develop regression models such as:
     - **Linear Regression** ➖
     - **Random Forest** 🌳
     - **XGBoost** ⚡

4. **Model Evaluation**: 
   - Use **Mean Squared Error (MSE)** 📉 and **R²** 📈 to evaluate the models.

5. **Feature Importance Analysis**: 
   - Identify key factors affecting song popularity 💡.

---

## 🏆 Evaluation

The main question this project will answer is: **What factors most influence a song’s popularity?** 🎤

We will evaluate the following models using **MSE** and **R²**:
- **Linear Regression** ➖
- **Random Forest** 🌳
- **XGBoost** ⚡

Secondary questions include:
- Which song features (e.g., danceability, energy, genre) have the greatest impact on popularity? 💃🎶
- How do these factors vary across different genres and subgenres? 🎧

By answering these questions, we aim to provide valuable insights for the music industry, helping stakeholders make informed decisions on song production and marketing strategies. 🎶

---

