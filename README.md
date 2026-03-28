# VIP2VIP: A Multi-Dimensional Pipeline for Holistic Prosodic Visualization

**VIP2VIP** (Visualize Intonation and Prosody for Voices of Italian Poets) is an open-source Python-based pipeline designed for the integrated visualization of fundamental frequency ($f_0$), intensity, and syllabic rate. While traditional speech research often privileges $f_0$ alone, this tool renders a multi-dimensional display to reveal how energy and tempo interact with pitch to cue prominence and phrasing.

## How It Works
The pipeline compresses three acoustic dimensions into a single coordinated display:
* **$f_0$ Contour:** Renders a smoothed pitch trace using either **LOWESS** or **GAM** (Generalized Additive Models).
* **Intensity:** Encoded as **line thickness** (instantaneous intensity); thicker segments indicate higher energy.
* **Syllabic Rate (SR):** Encoded as a **perceptually ordered color ramp** (e.g., green for slower rates, red for faster rates) projected directly onto the $f_0$ trace.

## Key Features
* **Superpositional Framework:** Designed to visualize global phrase-level trends alongside local accentual movements.
* **Auto Flex Smoothing:** Automatically adjusts smoothing parameters based on the number of syllables in a phrase to maintain visual comparability.
* **Micro-prosodic Robustness:** Sampling is restricted to voiced phonetic intervals to limit artifacts from voiceless consonants.
* **Reproducible Outputs:** Parameter choices are logged for each unit, and data can be exported as **CSV** for statistical analysis or **PNG** for publications.

---

## Requirements & Annotations
The pipeline is designed to run on lightweight, reproducible annotations.

### Software
* **Python** environment (Jupyter Notebook).
* **Core Libraries:** `Parselmouth` (Praat backend), `Matplotlib`, `statsmodels`, and `praatio`.

### Required Annotation Tiers (TextGrid)
Your Praat TextGrids must include the following tiers:
* **`CP` (Chunk/Prosodic Unit):** Defines the working window for plotting (e.g., interpausal units).
* **`syll` (Syllables):** Phonetic syllable intervals used to derive local and global syllabic rates.
* **`phon` (Voiced Segments):** Marks voiced intervals (vowels/voiced sonorants) for precise acoustic sampling.
* *Optional:* **`INT`** for intonational labels and **`VS`** for textual verse lines.

---

## Quick Start Guide

1.  **Environment Setup:** Ensure you have the required Python libraries installed:
    `pip install parselmouth-praat matplotlib statsmodels praatio`
2.  **Data Preparation:** Place your audio files and corresponding TextGrids (with `CP`, `syll`, and `phon` tiers) in your working directory.
3.  **Run the Pipeline:** Open the Jupyter Notebook and execute the visualization function.
4.  **Configure Smoothing:** Choose between **LOWESS** (default for local curvature) or **GAM** (for stable global trends) and enable **Auto Flex** for automatic smoothness scaling.
5.  **Interactive Selection:** Use the UI to batch process files or interactively select specific prosodic units (CPs) for detailed inspection.
6.  **Export:** Save the generated plots as images and extract the acoustic indices to a CSV file for further study.

---

## Citation
If you use this pipeline in your research, please cite the original paper:
> Lo Iacono, F., & Romano, A. (2026). *A Multi-Dimensional Pipeline for Holistic Prosodic Visualization: Integrating f0, Intensity, and Syllabic Rate using VIP2VIP. Speech Prosody 2026, Philadelphia, University of Pennsylvania*.

---
**License:** Open source. For issues or contributions, please visit the [official repository](https://github.com/fedeloiac/vip-pipeline).
