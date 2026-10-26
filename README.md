# Human Activity Recognition Using Hidden Markov Models

## Project Overview

This project uses Hidden Markov Models (HMMs) to recognise four human activities from smartphone sensor data: standing, walking, jumping, and staying still.

Accelerometer and gyroscope measurements are used to extract time-domain and frequency-domain features. Separate Gaussian HMMs are trained for each activity, and the Viterbi algorithm is used to decode hidden-state sequences and support activity classification.

## Activities

- Standing
- Walking
- Jumping
- Staying still

## Methodology

1. Collect accelerometer and gyroscope recordings for the four activities.
2. Inspect and preprocess the sensor data.
3. Divide recordings into overlapping two-second windows with a one-second stride.
4. Extract and standardise sensor features using a scaler fitted only on the training data.
5. Train one Gaussian HMM for each activity.
6. Classify unseen recordings using model log-likelihoods and evaluate performance.

## Evaluation

The initial evaluation used eight held-out recordings, with two recordings per activity. The models achieved **75% recording-level accuracy** on this test set.

Jumping and staying still were classified correctly in both test recordings. Standing and walking were each classified correctly in one of their two test recordings. These results are preliminary because the test set is small.

## Repository Structure

- `dataset/` — Labelled smartphone sensor data organised by activity (`standing`, `walking`, `jumping`, and `staystill`). Each activity contains accelerometer and gyroscope CSV files, with 100 CSV files per activity.
- `notebooks/` — Jupyter notebook containing data inspection, preprocessing, feature extraction, HMM training, Viterbi decoding, classification, and evaluation.
- `report/` — Project report covering the motivation, data collection, methodology, results, and discussion.

## Tools and Technologies

- Python
- Jupyter Notebook / Google Colab
- NumPy and pandas
- scikit-learn
- Matplotlib and Seaborn
- Hidden Markov Models

## Limitations

The evaluation uses a small held-out test set. The standing and walking HMMs also reached the configured maximum number of training iterations without meeting the convergence tolerance. Further testing and training would help assess and improve model reliability.

## Author

Hikma Hamza
