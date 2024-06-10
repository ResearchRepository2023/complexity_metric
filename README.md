# Research Dataset for the paper: Towards a developer-centric code understandability metric

## Overview
This repository contains datasets and preprocessing steps used in our research on analyzing EEG and eye tracking data for code comprehension tasks. We conducted experiments with 20 participants, each performing 4 code tasks chosen randomly in 4 runs. The datasets are structured for reproducibility and further analysis.

## Datasets
We have three important datasets in this experiment:
1. **EEG Data**
2. **Eye Tracking Data**
3. **Code Regions**

### EEG Data
**Raw Data:**
- 20 participants
- 20 `.cnt` files (named si_j, where i=1:20 for participants and j=1:4 for runs)

**Preprocessing:**
- Performed using EEGLAB (an interactive MATLAB toolbox)
- Steps include:
  1. EEG channel location setup
  2. Filtering: High-pass filter at 1 Hz and low-pass filter at 40 Hz
  3. Deleting useless segments
  4. Manual interpolation
  5. Referencing: Average reference
  6. ICA (Independent Component Analysis): Extended infomax using `runica`
  7. Artifact removal (manually operated)

**Final Structure:**
- `eeg_data.mat` includes 20 structs for 20 participants
- Each struct named `si_tj` (i=1:20 for participants, j=1:4 for tasks)
- Fields:
  - `eeg_data_struct.(field_name).feature` : Two features extracted
  - `eeg_data_struct.(field_name).time` : Corresponding time data

### Eye Tracking Data
**Raw Data:**
- 20 participants
- 20 `.mat` files

**Preprocessing:**
- Filtering invalid data points
- Calibration against code task images

**Final Structure:**
- `eye_data.mat` includes 20 structs for 20 participants
- Each struct named `si_tj` (i=1:20 for participants, j=1:4 for tasks)
- Fields:
  - `eye_data.code_time` : Time when participants read the code task
  - `eye_data.gaze_x` : Horizontal coordinates of eye gaze position
  - `eye_data.gaze_y` : Vertical coordinates of eye gaze position

### Code Regions
- Defined in the file `study0_1_tasks_regions.xlsx`
- Contains the regions of interest for the code tasks

## Models and Analysis
For the final model analysis, we tried 7 different models (2 linear and 5 non-linear) to analyze the data.

## Data Access
You can access all the data used in this research through the following Google Drive link:

[Access the Data](https://drive.google.com/drive/folders/1tFoCChdtkplacf0LPb4Z0tkz94Zrcs9d)

## Usage
1. **Download the datasets:**
   - `eeg_data.mat`
   - `eye_data.mat`
   - `study0_1_tasks_regions.xlsx`

2. **Preprocessing:**
   - Follow the steps mentioned above using EEGLAB and MATLAB for EEG data.
   - Use MATLAB for preprocessing eye tracking data.

3. **Analysis:**
   - Use the preprocessed data for running the models.
   - Example code and scripts will be provided in the `scripts` directory.

## Tools and Software
- **EEGLAB**: [EEGLAB Website](https://sccn.ucsd.edu/eeglab/index.php)
- **MATLAB**: For data preprocessing and analysis.


