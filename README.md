# Research Dataset for Developing Data-Driven Developer-Centric Software Complexity Metrics

## Open Science Commitment

This repository follows Open Science principles, including providing full access to data, preprocessing scripts, and analysis results to ensure reproducibility and transparency. The datasets are publicly available under the [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) license via Zenodo. All data, including EEG and eye-tracking data, code regions, and associated preprocessing scripts, are available for reuse and repurposing.

## Overview

This repository contains datasets and preprocessing steps used in our research on analyzing EEG and eye tracking data for code comprehension tasks. We conducted experiments with 35 participants, each performing 4 code tasks chosen randomly in 4 runs. The datasets are structured for reproducibility and further analysis.

## Datasets

We have three important datasets in this experiment:

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

## Data Access

You can access all the data used in this research through the following Zenodo link:

[Access the Data on Zenodo](https://zenodo.org/record/15106502)

## Licensing and Data Availability

The datasets and preprocessing scripts used in this study are available at [Zenodo](https://zenodo.org/record/15106502). The repository includes EEG data, eye tracking data, code regions, and analysis scripts, all released under open licenses to promote transparency and reproducibility.

## Contact

If you have any questions or issues with the datasets or preprocessing steps, feel free to contact the authors via the GitHub repository's issues section.

