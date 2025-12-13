# Hybrid Classical–Quantum Split Learning for Privacy-Preserving IoMT Analytics

[![Research Status](https://img.shields.io/badge/status-baseline%20phase-yellow)]()
[![Python](https://img.shields.io/badge/python-3.10%2B-blue)]()
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0%2B-red)]()

Research Repository — Baseline Models, Datasets, and Experiments

This repository contains the codebase for our ongoing research on **Hybrid Classical–Quantum Split Federated Learning (HCQ-SFL)** for secure, privacy-preserving analytics in Internet of Medical Things (IoMT) environments.

Our primary goal is to develop a multi-layered learning pipeline where sensitive medical data remains on the client device, and learning is distributed across classical and quantum components.

---

## 🎯 Research Objective

To build a privacy-preserving, intrusion-resilient learning framework for IoMT systems using:

- **Client-side classical neural networks** (for raw medical data processing)
- **Split Learning** (activations sent instead of raw data)
- **Federated Learning principles** (multi-client learning)
- **Quantum Machine Learning layer** (server-side anomaly detection + intrusion detection)
- **Multi-dataset evaluation** across physiological and IoT traffic datasets

This repository currently focuses on the **baseline classical models**, which form the foundation for the upcoming split learning and quantum stages.

---

## 📚 Datasets Used

We are working with multiple datasets to ensure robustness across medical and IoT environments:

### 1. WESAD (Wearable Stress & Affect Detection)
- 8-channel physiological signals (ACC, ECG, EMG, EDA, RESP, Temp)
- Sampling frequency: 700 Hz
- Used for emotion/stress classification

### 2. PAMAP2
- Physical activity monitoring (IMU + HR sensors)
- Used for human activity recognition (HAR)

### 3. MIMIC-III Waveform Dataset
- Clinical physiological waveforms (ECG, PPG, respiration, BP signals)
- Used for medical condition detection and critical care analytics

### 4. TON-IoT
- IoT telemetry + network intrusion traces
- Used for adversarial evaluation and intrusion detection modules

Each dataset has an independent end-to-end neural network implementation stored in `./models/`.

---

## 🧠 Current Progress (Baseline Phase)

We have built end-to-end neural network baselines for:

- ✅ WESAD
- ✅ PAMAP2
- ✅ MIMIC-III (Waveform)
- ✅ TON-IoT

### These baseline models serve two purposes:

1. **Benchmarking** raw performance before introducing distributed models
2. **Extracting** classical architectures that will become the client-side models in Split Learning

---

## 🧩 Planned Architecture (HCQ-SFL Pipeline)

The project will evolve into a multi-component architecture:

### 1. Client-Side Models (Current Phase)
- Conv1D-based feature extractors for raw medical signals
- Models trained locally on raw datasets
- Outputs intermediate activations (not raw data)

### 2. Split Learning (Next Phase)
- Activation vectors sent to server
- Server continues forward pass
- Gradient returned for client-backprop
- Raw data never leaves client

### 3. Federated Split Learning
- Multiple clients across datasets
- Server aggregates model updates or server-weight contributions

### 4. Quantum Machine Learning Layer
- Server-side quantum kernel or PQC layer
- Anomaly detection + adversarial robustness
- Improves intrusion resistance in IoMT networks

### 5. Evaluation Across Multi-Datasets
- Accuracy
- F1 score
- Communication cost
- Gradient leakage
- Privacy preservation metrics
- Adversarial performance

---

## 📁 Repository Structure

```
📦 root/
│
├── models/
│   ├── wesad_s2.ipynb
│   ├── pamap2_nn.ipynb
│   ├── mimic3_waveform.ipynb
│   ├── ton_iot_model.ipynb
│   └── ... (baseline NN implementations)
│
├── split_learning/
│   ├── client_model.py       # Will contain SL client-side networks
│   ├── server_model.py       # Will contain SL server-side networks
│   ├── train_split.py        # Planned split-learning training loop
│
├── quantum/
│   ├── qml_layer.py          # Placeholder for quantum circuit/pennylane layer
│   ├── qml_experiments.ipynb
│
├── data/
│   └── (Dataset loaders, preprocessing scripts)
│
└── README.md
```

---

## 🚀 How to Run the Baseline Models

Each notebook is self-contained. For example, to run the WESAD baseline:

1. Navigate to `models/wesad_s2.ipynb`
2. Download the WESAD dataset (instructions in notebook)
3. Run all cells

Repeat similarly for PAMAP2, MIMIC-III, and TON-IoT models.

---

## 🔧 Requirements

### Core Dependencies
- Python 3.10+
- PyTorch 2.0+
- NumPy
- Pandas
- SciPy
- Matplotlib / Seaborn
- scikit-learn

### Installation

Install basic dependencies:

```bash
pip install torch numpy scipy scikit-learn matplotlib pandas seaborn
```

**Note:** Quantum modules (PennyLane or Qiskit) will be added in later phases.

---

## 🤝 Contributors

**Research Team:**
- Students from North South University, BUET, KUET

**Advisor:**
- Faculty, Department of ECE, NSU

**Research Focus:**
- IoMT Security
- Split Learning
- Quantum Machine Learning
- Multimodal Sensor Analytics

---

## 📌 Project Status

| Phase | Status |
|-------|--------|
| Baseline models implemented | ✅ Complete |
| Dataset processing | ✅ Complete |
| Repository structure organized | ✅ Complete |
| Split Learning implementation | 🔄 In Progress |
| Multi-client Split Federated pipeline | ⬜ Planned |
| Quantum Layer integration | ⬜ Planned |
| Final hybrid system + adversarial experiments | ⬜ Planned |
| Paper writing and Q1 submission | ⬜ Planned |

---

## 📄 License

This research project is currently under development. License information will be updated upon publication.

---

## 📧 Contact

For questions or collaboration inquiries, please contact the research team through the respective institutions.

---

## 🔖 Citation

If you use this work in your research, please cite our upcoming paper (details to be added).

---

