==================================================================

Hybrid Classical–Quantum Split Learning for Privacy-Preserving IoMT Analytics
Research Repository — Baseline Models, Datasets, and Experiments

This repository contains the codebase for our ongoing research on Hybrid Classical–Quantum Split Federated Learning (HCQ-SFL) for secure, privacy-preserving analytics in Internet of Medical Things (IoMT) environments.
Our primary goal is to develop a multi-layered learning pipeline where sensitive medical data remains on the client device, and learning is distributed across classical and quantum components.

🎯 Research Objective

To build a privacy-preserving, intrusion-resilient learning framework for IoMT systems using:

Client-side classical neural networks (for raw medical data processing)

Split Learning (activations sent instead of raw data)

Federated Learning principles (multi-client learning)

Quantum Machine Learning layer (server-side anomaly detection + intrusion detection)

Multi-dataset evaluation across physiological and IoT traffic datasets

This repository currently focuses on the baseline classical models, which form the foundation for the upcoming split learning and quantum stages.

📚 Datasets Used

We are working with multiple datasets to ensure robustness across medical and IoT environments:

1. WESAD (Wearable Stress & Affect Detection)

8-channel physiological signals (ACC, ECG, EMG, EDA, RESP, Temp)

Sampling frequency: 700 Hz

Used for emotion/stress classification

2. PAMAP2

Physical activity monitoring (IMU + HR sensors)

Used for human activity recognition (HAR)

3. MIMIC-III Waveform Dataset

Clinical physiological waveforms (ECG, PPG, respiration, BP signals)

Used for medical condition detection and critical care analytics

4. TON-IoT

IoT telemetry + network intrusion traces

Used for adversarial evaluation and intrusion detection modules

Each dataset has an independent end-to-end neural network implementation stored in ./models/.

🧠 Current Progress (Baseline Phase)

We have built end-to-end neural network baselines for:

WESAD

PAMAP2

MIMIC-III (Waveform)

TON-IoT

These baseline models serve two purposes:

Benchmarking raw performance before introducing distributed models

Extracting classical architectures that will become the client-side models in Split Learning

🧩 Planned Architecture (HCQ-SFL Pipeline)

The project will evolve into a multi-component architecture:

1. Client-Side Models (Current Phase)

Conv1D-based feature extractors for raw medical signals

Models trained locally on raw datasets

Outputs intermediate activations (not raw data)

2. Split Learning (Next Phase)

Activation vectors sent to server

Server continues forward pass

Gradient returned for client-backprop

Raw data never leaves client

3. Federated Split Learning

Multiple clients across datasets

Server aggregates model updates or server-weight contributions

4. Quantum Machine Learning Layer

Server-side quantum kernel or PQC layer

Anomaly detection + adversarial robustness

Improves intrusion resistance in IoMT networks

5. Evaluation Across Multi-Datasets

Accuracy

F1 score

Communication cost

Gradient leakage

Privacy preservation metrics

Adversarial performance
