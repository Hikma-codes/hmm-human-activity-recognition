# Human Activity Recognition Using Hidden Markov Models

## Project Overview

This project explores human activity recognition using Hidden Markov Models (HMMs) and smartphone sensor data. It focuses on four activities: standing, walking, jumping, and staying still.

Accelerometer and gyroscope measurements are used to extract time-domain and frequency-domain features. A separate Gaussian HMM is trained for each activity, and model log-likelihoods are used to classify unseen recordings, with the Viterbi algorithm used to decode hidden-state sequences.

## Activities

- Standing
- Walking
- Jumping
- Staying still

## Getting Started

### 1. Clone the Repository

Open a terminal and run:

```bash
git clone https://github.com/Hikma-codes/hmm-human-activity-recognition.git
cd hmm-human-activity-recognition
```

### 2. Set Up the Environment

This project uses Python and Jupyter Notebook. The notebook can be opened and run using Google Colab or a local Python environment.

The main libraries used include:

- NumPy
- pandas
- scikit-learn
- Matplotlib
- Seaborn
- SciPy

To install the dependencies in a local Python environment, run:

```bash
pip install numpy pandas scikit-learn matplotlib seaborn scipy
```

### 3. Open the Notebook

Navigate to the `notebooks/` directory and open:

`HMM_Human_Activity_Recognition.ipynb`

You can open it using Jupyter Notebook or upload it to Google Colab.

### 4. Access the Dataset

The `dataset/` directory contains the processed sensor data, organised by activity. Each activity has separate accelerometer and gyroscope CSV files.

The original sensor recordings were collected and stored as ZIP files. The notebook's original data-loading workflow uses these ZIP recordings from Google Drive. To reproduce that workflow, the original ZIP files must also be available in the expected Google Drive folder.

## Methodology

1. Collect smartphone accelerometer and gyroscope recordings for the four activities.
2. Inspect and preprocess the sensor data.
3. Divide recordings into overlapping two-second windows with a one-second stride.
4. Extract sensor features and standardise them using a scaler fitted only on the training data.
5. Train a separate Gaussian HMM for each activity.
6. Classify held-out recordings using model log-likelihoods and evaluate the results.

## Evaluation

The initial evaluation used eight held-out recordings, with two recordings per activity. The models achieved **75% recording-level accuracy** on this test set.

Both jumping recordings and both staying-still recordings were classified correctly. One of the two standing recordings and one of the two walking recordings were classified correctly.

These results are preliminary because the test set is small. The standing and walking models also reached the configured maximum number of training iterations without meeting the convergence tolerance.

## Repository Structure

- `dataset/` — Labelled smartphone sensor data organised by activity (`standing`, `walking`, `jumping`, and `staystill`). Each activity contains 100 CSV files across the accelerometer and gyroscope folders, giving 400 CSV files in total.
- `notebooks/` — Jupyter notebook containing data inspection, preprocessing, feature extraction, HMM training, Viterbi decoding, classification, and evaluation.
- `report/` — Project report covering the motivation, data collection, methodology, results, and discussion.

## Tools and Technologies

- Python
- Jupyter Notebook and Google Colab
- NumPy and pandas
- scikit-learn
- Matplotlib and Seaborn
- Hidden Markov Models

## Limitations and Future Work

The evaluation is based on a small held-out test set, so the reported accuracy may not represent performance on a wider range of recordings. The standing and walking HMMs also reached the maximum number of training iterations without meeting the convergence tolerance. Future work could include evaluating more held-out recordings, investigating confusion between standing and walking, and further tuning the model training process.

## Author

Hikma Hamza