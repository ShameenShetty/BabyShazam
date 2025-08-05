# 🎵 Baby Shazam – Music Identification System

A Python program that identifies the five songs most similar to a test song using signal processing and frequency-based signature matching. Think of it as a simplified, educational version of Shazam.

## 📌 Overview

This project analyzes `.wav` audio files, extracts dominant frequencies using spectrograms, and compares them using one-norm (L1 norm) distance. It visualizes the spectrograms of the test song and its two closest matches for intuitive comparison.

## 🧠 How It Works

1. **Signature Extraction**:
   - For each song (including a test song), it computes a spectrogram and collects the dominant frequency at each time slice as the song's signature.

2. **Similarity Matching**:
   - Calculates the L1 distance between the test song's signature and every song in the database (`song-*.wav`).
   - Sorts the songs by ascending one-norm distance to find the top 5 closest matches.

3. **Visualization**:
   - Displays spectrograms of the test song and the two closest matches for comparison.

## 🛠️ Tech Stack

- **Language**: Python
- **Libraries**:
  - `numpy`
  - `scipy`
  - `soundfile`
  - `matplotlib`
  - `glob`

## 📂 File Structure

```
baby-shazam/
│
├── testSong.wav                  # Song to identify
├── song-01.wav ... song-64.wav  # Song database
├── main.py                      # Contains the classifyMusic() function
└── README.md
```

## 📦 Installation

Install dependencies with:

```bash
pip install numpy scipy matplotlib soundfile
```

## ▶️ Usage

Ensure all `.wav` files are in the same folder as `main.py`, and name your test song `testSong.wav`.

Then run:

```bash
python main.py
```

## 📝 Sample Output

```
415  song-bagpipe.wav
532  song-ballad.wav
641  song-bartok.wav
684  song-corea1.wav
701  song-corea2.wav
```

- The numbers represent L1 distances from the test song.
- A lower number indicates a higher similarity.

### 🎨 Visualization

After running the program, spectrograms of the test song and its two closest matches are displayed in separate windows using `matplotlib`.

## 📌 Notes

- The comparison method is based on frequency-domain signal processing and is not robust to noise, pitch changes, or tempo variations.
- This project is from a college homework assignment and not optimized for real-world use cases like the Shazam algorithm (which uses audio fingerprinting).


---