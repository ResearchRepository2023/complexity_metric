# Research Dataset for Developing Data-Driven Developer-Centric Software Complexity Metrics

## Overview

This repository contains datasets and preprocessing steps used in our research on analyzing EEG and eye tracking data for code comprehension tasks. We conducted experiments with 35 participants, each performing 4 code tasks chosen randomly in 4 runs. The datasets are structured for reproducibility and further analysis.

## Datasets

We have three important datasets in this experiment:

1. **EEG Data**
2. **Eye Tracking Data**
3. **Code Regions**

### EEG Data

#### Raw Data:

- 35 participants
- 20 `.cnt` files (named `si_j`, where `i=1:20` for participants and `j=1:4` for runs)

#### Preprocessing:

Preprocessing was performed using **EEGLAB**, an interactive MATLAB toolbox. The following steps were applied:

- **EEG channel location setup**
- **Filtering**:
  - High-pass filter at 1 Hz
  - Low-pass filter at 40 Hz
- **Data cleaning**:
  - Deleting useless segments
  - Manual interpolation
- **Referencing**: Average reference
- **ICA (Independent Component Analysis)**: Extended Infomax using `runica`
- **Artifact removal**: Manually operated

#### Final Structure:

The processed EEG data is stored in `eeg_data.mat` and contains 20 structs, one for each participant. Each struct is named `si_tj` (where `i=1:20` for participants, `j=1:4` for tasks). The struct contains the following fields:

- `eeg_data_struct.(field_name).feature`: Two features extracted from the data
- `eeg_data_struct.(field_name).time`: Corresponding time data

### Eye Tracking Data

#### Raw Data:

- 35 participants
- 35 `.mat` files

#### Preprocessing:

- Filtering invalid data points
- Calibration against code task images

#### Final Structure:

The processed eye tracking data is stored in `eye_data.mat`, which contains 35 structs for 35 participants. Each struct is named `si_tj` (where `i=1:35` for participants, `j=1:4` for tasks). The struct contains the following fields:

- `eye_data.code_time`: Time when participants read the code task
- `eye_data.gaze_x`: Horizontal coordinates of eye gaze position
- `eye_data.gaze_y`: Vertical coordinates of eye gaze position

### Code Regions

The regions of interest for the code tasks are defined in the file `study0_1_tasks_regions.xlsx`.

## Models and Analysis

For the final model analysis, we evaluated 7 different models (2 linear and 5 non-linear) to analyze the data.

## Survey for Volunteers

This survey was distributed to volunteers/participants to assess their experience level and collect relevant data. 

[Click here to view the survey](#)

## Data Access

You can access all the data used in this research through the following Zenodo link:

[Access the Data on Zenodo](https://zenodo.org/record/15106502?token=eyJhbGciOiJIUzUxMiJ9.eyJpZCI6ImQyMDIwZjNlLTllZmYtNDcyZC1iZDNiLWU5NDg3ODgyMjFiZSIsImRhdGEiOnt9LCJyYW5kb20iOiJiMTZlMjEzMzFkZjYyY2Q2YWE3MWNiMWU2NDhjNzhhMyJ9.NZZdkoi_MphzIehf3gricOUBnFLz04vUkNd-230n6lQLGh12hWfTeIpjtg3UzNjT_jLejPVQMv4wE_JAZvN3wA)

## Usage

### Download the datasets:

- `eeg_data.mat`
- `eye_data.mat`
- `study0_1_tasks_regions.xlsx`

### Preprocessing:

- Follow the steps mentioned above using **EEGLAB** and **MATLAB** for EEG data.
- Use **MATLAB** for preprocessing eye tracking data.

### Analysis:

Use the preprocessed data to run the models. Example code and scripts will be provided in the `scripts` directory.

## Tools and Software

- **EEGLAB**: [EEGLAB Website](https://sccn.ucsd.edu/eeglab/index.php)
- **MATLAB**: For data preprocessing and analysis.

## Licensing and Data Availability

The datasets and preprocessing scripts used in this study are available at [Zenodo](https://zenodo.org/record/15106502?token=eyJhbGciOiJIUzUxMiJ9.eyJpZCI6ImQyMDIwZjNlLTllZmYtNDcyZC1iZDNiLWU5NDg3ODgyMjFiZSIsImRhdGEiOnt9LCJyYW5kb20iOiJiMTZlMjEzMzFkZjYyY2Q2YWE3MWNiMWU2NDhjNzhhMyJ9.NZZdkoi_MphzIehf3gricOUBnFLz04vUkNd-230n6lQLGh12hWfTeIpjtg3UzNjT_jLejPVQMv4wE_JAZvN3wA). The repository includes EEG data, eye tracking data, code regions, and analysis scripts, all released under open licenses to promote transparency and reproducibility.

## Open Science Policies

This research follows the open science principles set forth by the ACM SIGSOFT initiative. The data, analysis scripts, and other artifacts are made openly available for reuse and repurposing to encourage transparency and reproducibility.

- Artifacts are available without any barrier (no paywalls, registration forms, etc.).
- All data and code are stored and archived in publicly accessible repositories (Zenodo).
- Data is made available under an open data license (CC0 1.0 or CC-BY 4.0).
- Software, if applicable, is released under an open source license.

## Contact

If you have any questions or issues with the datasets or preprocessing steps, feel free to contact the authors via the GitHub repository's issues section.
