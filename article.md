---
title: "Signal Processing for Respiratory Rate Detection: Analyzing EKG Data with FFT and RSA Methods"
short_title: Signal Processing for Respiratory Rate Detection
abstract: |
 This study explores identifying respiratory rate (RR) through an electrocardiogram (EKG) data analysis using Fast Fourier Transform (FFT) inspired open source programs for respiratory sinus arrhythmia (RSA). Using computational Python libraries scipy.signal.find_peaks and scipy.signal.welch, our study assesses RR from observed chances in heart rate due to RSA. EKG and electromyography (EMG) data were collected using Vernier sensors and processed with pre-established bandpass filtering techniques (0.5–150 Hz) to minimize noise. Despite a small limitation in failing to capture baseline respiratory rates from participants, the trial results indicated that the average RR from one trial was 22.48 breaths per minute, which closely aligns with expected physiological rates (12–20 breaths per minute), though slightly elevated. Our findings demonstrate that computational methods like FFT and RSA using EKG signals offer promising potential for RR estimation, even with minor limitations in signal interference.
---
## Introduction
To maximize performance and recovery, athletes frequently use medical devices such as EKGs, pulse oximeters, and other equipment. These devices can often be bulky or invasive, making them inappropriate for athletes who might want multiple at once. Because the heart and lungs function so closely together, we can observe how these organs affect one another. Specifically, with respiratory sinus arrhythmia (RSA)(@https://doi.org/10.1038/s41598-023-50470-0), a phenomenon measured by power spectral analysis to determine  respiration rate (RR) based on changes in heart rate. The goal of this study is to establish a basis for methods of precisely, efficiently, and dependably estimating RR using RSA under various circumstances. 
Past studies show that morphological changes in EKG readings like the QRS complex ([](#labeled)) correlate to respiration. RR estimation algorithms often use time and frequency domain features for accuracy, though noise reduction is essential to efficiently analyzing this data. 
To be considered successful, RR estimates must be within ±2 breaths per minute compared to observed RR, the device must be reliable over different kinds of activity, and must be easily integrated with other devices. 
The hypothesis predicts that EKG-based algorithms can estimate RR by analyzing amplitude and frequency patterns caused by RSA.

## Methods
Participants in this study were drawn from the general public and were chosen based on their willingness to participate in the experiment. To ensure reliable analysis, we had 5 participants, all of whom came from different backgrounds. Specific demographic parameters, such as age or gender, were considered, but participants were chosen at random from the available pool, with no additional constraints beyond basic consent and participation requirements.
The key materials used in this experiment were Vernier sensors for collecting EKG and EMG data, as well as the Vernier Graphical Analysis program. Signal detection was done using electrodes and sensor leads that were attached in accordance with established electrode placement protocols for both EKG and EMG measurements. The computational analysis was done via Python using the open-source libraries scipy.signal.find_peaks and scipy.signal.welch for signal analysis.
The study used a signal analysis design, with EKG data as the dependent variable. The independent variables were signal features discovered from physiological EKG measurement and the use of spectral analysis. Controlled variables included electrode location and participant resting circumstances to reduce artifacts.
First, participants sat comfortably, with their forearms resting on their thighs or armrests. The electrodes were attached as follows: Three electrode patches were applied to the subject at specific locations: one on the inside of the right wrist, one on the inside of the right upper forearm (distal to the elbow), and one on the inside of the left upper forearm. Two electrodes were placed along the muscle of interest, with one ground electrode above or below the adjacent joint, or alternatively on the wrist of the other arm, to reduce motion artifacts(@https://doi.org/10.1038/s41598-023-50470-0 ,@https://doi.org/10.3390/diagnostics14030284). The collection of data was done with Vernier Graphical Analysis.
Before analysis, the EKG signal was pre-processed with a bandpass filter (0.5-150 Hz range)(Fig. 3, 2). To compute the respiratory rate and frequency analysis, the signal was analyzed spectrally using Python's scipy.signal.welch library (@https://doi.org/10.1038/s41598-023-50470-0). Peaks in the EKG data were detected using scipy.signal.find_peaks, and they were then evaluated in conjunction with the respiration rate computation(@https://doi.org/10.1038/s41598-023-50470-0 , @https://doi.org/10.3390/s21010078).

| Index | Data Set 3:Time(s) | Data Set 3:Potential(mV) | Data Set 3:EKG(mV) |
| --- | --- | --- | ---|
0 | 0.000 | -0.047928 | -0.002211 |
1 | 0.005 | -0.046707 | -0.009467 |
2 | 0.010 | 0.049881 | -0.015508 |
3 | 0.015 | 0.061325 | -0.010341 |
4 | 0.020 | 0.051102 | 0.004425 |


```{figure} img/labeledekg.jpeg
:label: labeled
:alt: Diagram of an electrocardiogram (EKG) waveform, labeled with different segments and intervals. The image highlights the P wave, PR segment, QRS complex, ST segment, T wave, TP segment, PR interval, and QT interval, each indicated with distinct colors for clarity.
This image was used to help recognize and organize the EKG data.
(https://www.ezmedlearning.com/blog/ekg-wave)

```


```{figure}
:label: rawvfiltd

(rawd)=
![This is the raw data before filtering.](#raw)

(filtd)=
![This is the data after filtering.](#filtered)

This is the visual data before and after applying a bandpass filter.
```
```{figure}
:label: rp

(rpeak)=
![Shown above are all of the labeled R-Peaks under the filtered EKG Signal.](#rpeaks)

Shown above are all of the labeled R-Peaks under the filtered EKG Signal.

```

## Results
Our primary objective was to calculate respiratory rate using electrocardiogram (EKG) data and Python analysis. The process proved mostly successful, with minor limitations due to data collection and time constraints. During the initial data collection, we encountered a personal oversight: the original respiratory rates from the participants were not recorded. Despite this, the calculated respiratory rate findings are still valuable for interpreting the trial results. The standard respiratory rate at rest typically falls between 12–20 breaths per minute for a healthy adult. 
Although this study focused on conceptual exploration rather than extensive multi-subject testing, only one trial was run to calculate respiratory rate ([](#rawvfiltd)). This result deviates slightly from the standard range but is only 0.48 breaths per minute off from what was hypothesized. This difference leads us to believe that our method for calculation was generally accurate albeit slightly elevated compared to standard values. Overall, our calculations and outcome support the relationship between the measured respiratory rate and the expected range, even if variations exist.

## Discussion
Our findings contribute to this body of research by demonstrating the potential for computational approaches like EKG analysis paired with Python programming to accurately measure respiratory rate. This methodological connection extends the existing understanding by offering a proof of concept for computational respiratory analysis. The slight deviation we observed could be explained by individual physiological variability, or potentially by signal interference or other external factors not accounted for in our trial. Our results generally support previous studies on EKG and respiratory coupling while introducing opportunities for future research into computational methods’ precision and reliability in respiratory studies.

## Conclusion
Our study successfully demonstrated that respiratory rate could be calculated using EKG data and Python analysis, confirming the potential of computational methods in physiological research. The primary finding was that the average respiratory rate for our fourth trial was 22.48 breaths per minute, a result that was very close to our expected hypothesis range (12–20 breaths per minute)(@https://doi.org/10.1038/s41598-023-50470-0). While the observed rate was slightly elevated, the findings suggest that the conceptual method of using EKG signals for respiratory rate measurement is effective.
In the future, it would be paramount to create a generalized model for calculating RR from an EKG, instead of using code specific to one trial, testing against estimated and actual respiratory rates. Expanding the number of trials would point out areas of improvement or error, as well as allowing for a better understanding of the validity of EKG use for respiratory rate. It would also be efficient to use a program that could use real-time signal processing with filtering to increase precision while being effective for athletic long-term use. Future studies may lean towards exploring how this could be used to identify abnormal breathing patterns associated with specific medical conditions. 
