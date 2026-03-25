# Beyond the Login: Profiling Digital Behavior of Public WiFi Users in Indonesia

This project analyzes user behavior patterns from public WiFi hotspot login data across major Indonesian cities. The analysis covers demographic segmentation, device preferences, digital interest levels, and login time patterns to extract actionable business insights for location based digital marketing.

## Project Context

A startup providing WiFi marketing solutions needs to understand who connects to their hotspots, when they connect, and what their digital engagement level looks like. This project simulates that scenario using synthetic data that mirrors the structure and distribution of real world hotspot login records.

## Dataset Overview

500 synthetic user records, each containing:

**Base Variables (from raw login data)**

| Variable | Description |
|---|---|
| Nama Lokasi | City or area where the WiFi hotspot is located |
| Jam Login | Time the user logged in (HH:MM format) |
| Nama | Full name of the user |
| Email | Email address used during login |
| No Telepon | Phone number |
| Tahun Lahir | Birth year |
| Merk HP | Device brand detected at login |
| Minat Digital | Self reported or inferred digital interest level |
| Tipe Lokasi | Classification of the hotspot location (Urban, Suburban, Tourism) |

**Derived Variables (feature engineering)**

| Variable | Source | Logic |
|---|---|---|
| Usia | Tahun Lahir | Current year minus birth year |
| Generasi | Tahun Lahir | Gen Z, Millennial, Gen X, Boomer |
| Waktu Sesi | Jam Login | Pagi, Siang, Sore, Malam |
| Skor Minat Digital | Minat Digital | Numeric score (25, 50, 75, 95) |
| Status Aktif | Jam Login | Active if login falls in peak hours |
| Domain Email | Email | Domain extracted from email address |

## Analysis Performed

1. Exploratory Data Analysis: distribution of users by location, device market share, digital interest breakdown, age histogram, login hour heatmap
2. Confidence Interval (95%): calculated for mean user age and mean digital interest score using t distribution

## Key Results

| Metric | Mean | 95% CI Lower | 95% CI Upper |
|---|---|---|---|
| Average Age | 37.75 | 36.83 | 38.67 |
| Average Digital Interest Score | 59.66 | 57.73 | 61.59 |

## Project Structure

```
.
|   README.md
|   requirements.txt
|   dummy_data_higo.ipynb
|   Beyond the Login - Profiling Digital Behavior of Public WiFi Users in Indonesia.pptx
|
+-- data/
        dummy_data_digital_users.csv
        ci_summary.csv
```

## Requirements

Python 3.10 or higher. Install dependencies before running the notebook:

```
pip install -r requirements.txt
```

Jupyter environment (JupyterLab, VS Code with Jupyter extension, or Google Colab) is required to run the .ipynb file.

## How to Run

1. Clone this repository
2. Install the required packages: `pip install -r requirements.txt`
3. Open `dummy_data_higo.ipynb` in your Jupyter environment
4. Run all cells from top to bottom
5. Output CSV files will be saved to the `data/` folder

## Notes

The dataset is entirely synthetic, generated using the Faker library with Indonesian locale (id_ID). No real personal data is used. The data distributions (device brand weights, interest level proportions, login hour patterns) are designed to approximate realistic scenarios for the Indonesian market.

## Author

Qodri
