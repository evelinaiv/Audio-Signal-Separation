# Audio Signal Separation and Filtering with FFT and Gaussian Smoothing
## Overview

This project explores how **frequency-domain analysis** can be used to process and separate overlapping animal sounds from a mixed environmental recording.  
Using Python and the **Fast Fourier Transform (FFT)**, I transformed an audio signal into its frequency components, applied multiple filters, and visualized the results through **spectrograms** and reconstructed sound.

The notebook demonstrates a complete workflow in **digital signal processing** — from loading raw audio data to designing custom filters and comparing their effects on sound clarity and smoothness.

---

## Project Objectives

- Load and preprocess a real `.wav` file containing multiple animal calls.  
- Analyze the signal in both the **time domain** and **frequency domain** using FFT.  
- Create visualizations of the waveform, amplitude spectrum, and spectrogram.  
- Design and apply two custom filters:
  -  **Brick-Wall Band-Pass Filter:** sharply isolates a defined frequency range.  
  -  **Gaussian Band-Pass Filter:** provides a smoother transition between retained and removed frequencies.  
- Reconstruct the filtered audio with **Inverse FFT (iFFT)**.  
- Compare results visually and audibly to understand how filter design affects output quality.

---

##  Dataset

- **File:** `Jungle-SoundBible.com-1211567897.wav`  
- **Source:** [SoundBible](https://soundbible.com/) – a public collection of royalty-free sound effects.  
- **Description:**  
  The recording contains several overlapping **animal sounds** (birds, insects, frogs, etc.) recorded in a natural jungle environment.  
  It was selected to simulate a real-world bioacoustics problem: identifying distinct species’ sounds within a single mixed recording.

---

##  Methods

| Step | Description |
|------|--------------|
| **1. Signal Loading & Preprocessing** | Read the `.wav` file using `scipy.io.wavfile`, extracted one stereo channel, and calculated duration, number of samples, and sample rate. |
| **2. Frequency Analysis (FFT)** | Applied FFT to decompose the signal into its frequency spectrum, revealing dominant frequency bands corresponding to different animal sounds. |
| **3. Visualization** | Created time-series plots, amplitude spectra, and spectrograms using `matplotlib` and `scipy.signal.spectrogram` to visualize how energy varies across time and frequency. |
| **4. Brick-Wall Filtering** | Implemented a custom band-pass filter that zeros out all frequencies outside a chosen range. Used multiple frequency bands (e.g., 500–900 Hz, 900–1400 Hz, 2000–3500 Hz, 6000–8000 Hz) to isolate potential animal species. |
| **5. Gaussian Band-Pass Filtering** | Developed a smoother filter using a Gaussian kernel, producing softer transitions between preserved and suppressed frequencies. Compared against the brick-wall baseline. |
| **6. Reconstruction (iFFT)** | Reconverted filtered signals to the time domain using Inverse FFT and evaluated results through both waveform plots and audio playback. |

---

##  Results

- Successfully separated several animal sound ranges from the mixed jungle recording.  
- Visualized clear frequency bands corresponding to **low-**, **mid-**, and **high-frequency** animal calls.  
- Demonstrated that Gaussian filters produce **smoother, more natural transitions** in the frequency spectrum compared to brick-wall filters.  
- Highlighted how frequency-domain techniques can support tasks such as **noise reduction**, **species identification**, and **acoustic monitoring**.

---

##  Tools & Libraries

| Category | Tools Used |
|-----------|-------------|
| **Programming Language** | Python |
| **Signal Processing** | `NumPy`, `SciPy` |
| **Visualization** | `Matplotlib`, `Seaborn` |
| **Audio Handling** | `scipy.io.wavfile`, `IPython.display.Audio` |

---

##  Repository Structure

```

Audio-Signal-Separation/
│
├── Audio Signal Separation and Filtering with FFT and Gaussian Smoothing.ipynb   # Main notebook
├── Jungle-SoundBible.com-1211567897.wav                                   # Sample audio file
├── README.md                                                              # Project overview
├── LICENSE                                                                # MIT License
└── .gitignore                                                             # Environment ignores

```

---

##  Learning Outcomes

- Practical understanding of **Fourier Transform theory** applied to real-world audio.  
- Experience with **digital filtering**, **frequency analysis**, and **spectrogram interpretation**.  
- Ability to design custom filters and evaluate their effects on sound quality.  
- Strengthened skills in Python data visualization and scientific computing.

---

## Future Improvements

- Add **quantitative metrics** such as SNR or RMS energy to evaluate filter effectiveness.  
- Experiment with **automatic classification** of filtered animal sounds using simple ML models (e.g., CNN on spectrograms).  
- Apply similar filtering to other real-world audio datasets (urban noise, speech, music).

---

##  License

This project is released under the [MIT License](LICENSE).  
The included audio file originates from [SoundBible.com](https://soundbible.com/) and is used for educational purposes only.

---

##  Author

**Evelina Ivanova**  
MSc Data Science 
GitHub: [@evelinaiv](https://github.com/evelinaiv)

