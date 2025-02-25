# Emotion Analysis of Spotify Songs

This project analyzes the audio features of songs from a Spotify playlist to predict their emotional quadrant based on the Russell circumplex model of affect.

**Project Status:** The latest working code and development progress can be found in the Jupyter Notebook file named `9_multimodal.ipynb`. This README provides instructions assuming you are working with the code in that notebook.

## Overview

The Python script in `9_multimodal.ipynb` performs the following steps:

1.  **Loads Song Data:** Reads a CSV file containing a list of songs with their Spotify IDs.  A sample CSV file (`sample_input.csv`) is included for testing.
2.  **Spotify Authentication:** Uses the `spotipy` library and Spotify's OAuth 2.0 flow to authenticate with the Spotify Web API.  This requires a Spotify Developer account and application credentials.
3.  **Audio Feature Extraction:**  Retrieves audio features (danceability, energy, valence, etc.) for each song using the `sp.audio_features()` method.  This is done in batches to avoid API rate limits.
4.  **Data Processing:** Combines the audio features with the original song data.
5.  **Output:** Saves the combined data (original song data + audio features) to a new CSV file named `mi_dataframe_con_features.csv`.

## Dependencies

This project requires the following Python libraries:

*   `spotipy`: For interacting with the Spotify Web API.
*   `pandas`: For data manipulation and CSV file handling.
*   `requests`: For making HTTP requests (used internally by `spotipy`).

Install these libraries using `pip`:

```bash
pip install spotipy pandas requests