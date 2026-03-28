# VIP2VIP: A Multi-Dimensional Pipeline for Holistic Prosodic Visualization

[cite_start]**VIP2VIP** (Visualize Intonation and Prosody for Voices of Italian Poets) is an open-source Python-based pipeline designed for the integrated visualization of fundamental frequency ($f_0$), intensity, and syllabic rate[cite: 8, 195]. [cite_start]While traditional speech research often privileges $f_0$ alone, this tool renders a multi-dimensional display to reveal how energy and tempo interact with pitch to cue prominence and phrasing[cite: 7, 8, 17].

## ### How It Works
[cite_start]The pipeline compresses three acoustic dimensions into a single coordinated display[cite: 12, 111]:
* [cite_start]**$f_0$ Contour:** Renders a smoothed pitch trace using either **LOWESS** or **GAM** (Generalized Additive Models)[cite: 8, 87, 113].
* **Intensity:** Encoded as **line thickness** (instantaneous intensity); thicker segments indicate higher energy[cite: 8, 124].
* [cite_start]**Syllabic Rate (SR):** Encoded as a **perceptually ordered color ramp** (e.g., green for slower rates, red for faster rates) projected directly onto the $f_0$ trace[cite: 8, 110, 111, 124].

## ### Key Features
* **Superpositional Framework:** Designed to visualize global phrase-level trends alongside local accentual movements[cite: 10, 26, 48].
* [cite_start]**Auto Flex Smoothing:** Automatically adjusts smoothing parameters (degrees of freedom and penalty) based on the number of syllables in a phrase to maintain visual comparability[cite: 118, 119, 173].
* [cite_start]**Micro-prosodic Robustness:** Sampling is restricted to voiced phonetic intervals to limit artifacts from voiceless consonants[cite: 9, 95, 102].
* **Reproducible Outputs:** Parameter choices are logged for each unit, and data can be exported as **CSV** for statistical analysis or **PNG** for publications[cite: 89, 134, 135].

---

## ### Requirements & Annotations
The pipeline is designed to run on lightweight, reproducible annotations[cite: 9, 90].

### #### Software
* [cite_start]**Python** environment (Jupyter Notebook)[cite: 86].
* [cite_start]**Core Libraries:** `Parselmouth` (Praat backend), `Matplotlib`, `statsmodels` (for LOWESS/GAM), and `praatio`[cite: 86, 87, 88].

### #### Required Annotation Tiers (TextGrid)
[cite_start]Your Praat TextGrids must include the following tiers[cite: 90]:
* [cite_start]**`CP` (Chunk/Prosodic Unit):** Defines the working window for plotting (e.g., interpausal units)[cite: 88, 91].
* **`syll` (Syllables):** Phonetic syllable intervals used to derive local and global syllabic rates[cite: 88, 92, 100].
* [cite_start]**`phon` (Voiced Segments):** Marks voiced intervals (vowels/voiced sonorants) for precise acoustic sampling[cite: 88, 94, 95].
* [cite_start]*Optional:* **`INT`** for intonational labels and **`VS`** for textual verse lines[cite: 88, 96, 97].

---

## ### Quick Start Guide

1.  **Environment Setup:** Ensure you have the required Python libraries installed (`pip install parselmouth-praat matplotlib statsmodels praatio`).
2.  [cite_start]**Data Preparation:** Place your audio files and corresponding TextGrids (with `CP`, `syll`, and `phon` tiers) in your working directory[cite: 90, 100].
3.  [cite_start]**Run the Pipeline:** Open the Jupyter Notebook and execute the visualization function[cite: 86, 131].
4.  [cite_start]**Configure Smoothing:** Choose between **LOWESS** (default for local curvature) or **GAM** (for stable global trends) and enable **Auto Flex** for automatic smoothness scaling[cite: 113, 114, 118, 133].
5.  [cite_start]**Interactive Selection:** Use the UI to batch process files or interactively select specific prosodic units (CPs) for detailed inspection[cite: 131].
6.  [cite_start]**Export:** Save the generated plots as images and extract the acoustic indices to a CSV file for further study[cite: 135].

---

## ### Citation
If you use this pipeline in your research, please cite the original paper:
> Lo Iacono, F., & Romano, A. (2026). [cite_start]*A Multi-Dimensional Pipeline for Holistic Prosodic Visualization: Integrating $f_0$, Intensity, and Syllabic Rate using VIP2VIP. Speech Prosody 2026, Philadelphia, University of Pennsylvania.*. [cite: 1, 2]

---
**License:** Open source. [cite_start]For issues or contributions, please visit the [official repository](https://github.com/fedeloiac/vip-pipeline). [cite: 193]
