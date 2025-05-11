# Peripheral Signal Analysis using Empatica E4

## Overview
This project focuses on the **analysis of peripheral physiological signals** collected using the **Empatica E4 wristband**, with an emphasis on:

- **Galvanic Skin Response (GSR)**  
- **Heart Rate Variability (HRV)** derived from **Photoplethysmography (PPG)**

The goal is to explore signal patterns related to emotional states—specifically comparing **anxiety vs. normal states**.

---

## Methodology

### 1. GSR Signal Analysis
Power spectral density was computed for GSR signals in both emotional states. However, it was **difficult to establish clear patterns** due to:

- A limited number of signal samples  
- Possible unfiltered noise in the raw data  

### 2. HRV Analysis using PPG
Spectral analysis was performed using the **Welch method** on raw signals.

A comparison was made between:
- HRV computed from **PPG-derived peaks**  
- HRV based on **IBI (Inter-Beat Interval) values** directly extracted by the E4 device

Results showed that **IBI-based HRV closely resembles** the expected outcomes, more so than those obtained through manual processing of PPG signals. In the image, time, frequency, and power are plotted against each other for HRV calculated through PPG, and the one given by IBI

<img width="724" alt="image" src="https://github.com/user-attachments/assets/012753cf-68ee-402e-93da-a7ae31e2e5d2" />


---

## ⚠Considerations

- **IBI data is pre-processed** by the device, which discards noisy segments and movement-contaminated data using onboard accelerometer inputs.
- **Manual peak detection on raw PPG signals** includes noise-contaminated sections, likely increasing error.
- **Over-filtering** may explain unusually low heart rate values calculated from PPG data. Although filters used followed literature recommendations, many waveform details were lost.

This does not necessarily imply incorrect processing, but it may be **appropriate for medical-grade signal quality**.

---

## Technologies Used

- Python  
- SciPy & NumPy  
- Matplotlib  
- Pandas  
- Signal processing techniques (Welch method, filtering, Lomb)

---

## Conclusion

- The Empatica E4’s internal processing offers robust IBI-based HRV data, with better noise handling than manual peak detection.
- GSR analysis is limited by sample size and unfiltered noise, making it less reliable in this dataset.
- Filter design greatly influences PPG-derived HRV, highlighting the trade-off between noise suppression and signal fidelity.

---

## References


