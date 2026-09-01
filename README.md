# Adaptive Nonlinear Vector Autoregression (Adaptive NVAR)

<p align="center"><a href="https://arxiv.org/abs/2507.08738"><img src='https://img.shields.io/badge/arXiv-Paper-red?logo=arxiv&logoColor=white' alt='arXiv'></a>

This repository contains the code and datasets required to reproduce the experiments reported in:

**Adaptive Nonlinear Vector Autoregression: Robust Forecasting for Noisy Chaotic Time Series**

### Overview

Adaptive NVAR extends standard nonlinear vector autoregression by combining delay-embedded inputs with a shallow, trainable nonlinear feature map. The nonlinear feature transformation and linear readout are optimized jointly using gradient-based learning.

The method is evaluated on **Lorenz-63, Lorenz-96, and Mackey–Glass** systems under noise-free and noisy conditions. The repository also includes implementations of **standard NVAR, ESN, and HESN** used as baselines.

---

## Repository Contents

The main directories are organized by model and dynamical system:

```text
Adaptive NVAR L63/       Adaptive NVAR on Lorenz-63
Adaptive NVAR L96/       Adaptive NVAR on Lorenz-96
Adaptive NVAR MG/        Adaptive NVAR on Mackey–Glass

Standard NVAR L63/       Standard NVAR on Lorenz-63
ESN L63/                 Echo State Network on Lorenz-63
HESN L63/                Hybrid Echo State Network on Lorenz-63

Standard NVAR MG/       Standard NVAR on Mackey–Glass
ESN MG/                 Echo State Network on Mackey–Glass
HESN MG/                Hybrid Echo State Network on Mackey–Glass
```

Each experiment contains notebooks for:

* **Noise-free**
* **Low-noise**
* **Moderate-noise**
* **High-noise**

The corresponding `.npy` datasets are included where practical.

---

## Reproducing the Paper Results

### Option 1: Google Colab

Google Colab with a GPU is the easiest way to run the notebooks.

1. Open the relevant `.ipynb` notebook in Google Colab.
2. Select **Runtime → Change runtime type → GPU**.
3. Run the notebook cells sequentially.

The notebooks contain the experimental code, data loading, model training, and forecasting procedures needed to reproduce the reported experiments.

### Option 2: Local Installation

The code was developed and tested with **Python 3.12**.

```bash
git clone https://github.com/AzimovSherkhon/Adaptive-Nonlinear-Vector-Autoregression-Robust-Forecasting-for-Noisy-Chaotic-Time-Series.git
cd Adaptive-NVAR

conda create -n adaptive-nvar python=3.12
conda activate adaptive-nvar

pip install -r requirements.txt
```

Then launch Jupyter:

```bash
jupyter notebook
```

---

## GPU and Reproducibility

The experiments were tested on **NVIDIA A100 and H200 GPUs**.

Because chaotic forecasting can be sensitive to numerical differences, results obtained on other GPU architectures may differ slightly, particularly for long-horizon forecasts. For closest reproduction of the reported results, **A100 or H200 GPUs are recommended**.

---

## Datasets

The repository includes the **Lorenz-63** and **Mackey–Glass** datasets used in the experiments.

The **Lorenz-96 (100-variable)** dataset is provided separately because of its size:

**[Download Lorenz-96 Dataset](https://drive.google.com/drive/folders/1jpp847aD7VC_kR5oPfE_tBYsHsCrdGDu?usp=sharing)**

Noise levels are provided as separate datasets (including noise-free, 10%, 20%, and 30% cases where applicable).

---

## Running the Adaptive NVAR Model

To reproduce an experiment:

1. Navigate to the corresponding system and dataset directory.
2. Select the required noise-level notebook, for example:

```text
Adaptive NVAR L63/
└── Dataset 1/
    ├── Adaptive_NVAR_Noise-free.ipynb
    ├── Adaptive_NVAR_Low_noise.ipynb
    ├── Adaptive_NVAR_Moderate_noise.ipynb
    └── Adaptive_NVAR_High_noise.ipynb
```

3. Run the notebook cells sequentially.

The notebooks generate the model predictions and evaluation results used in the study.

---

## Using Adaptive NVAR with New Data

For experiments on a new time series:

1. Place the dataset in the appropriate **Adaptive NVAR** directory.
2. Use the grid-search notebook to identify suitable hyperparameters.
3. Run the prediction notebook using the selected parameters.
4. Evaluate the resulting multi-step forecasts.

---

## Reproducibility

The repository is intended to provide the computational materials needed to reproduce the experiments and comparisons presented in the paper, including:

* Adaptive NVAR experiments
* Standard NVAR baseline
* ESN baseline
* HESN baseline
* Noise-free and noisy forecasting experiments
* Dataset generation notebooks
* Forecasting and evaluation notebooks

--

## Citation

If you use this code or Adaptive NVAR in your research, please cite:

**Azimov, S. et al.** *Adaptive Nonlinear Vector Autoregression: Robust Forecasting for Noisy Chaotic Time Series.* [![DOI](https://arxiv.org/abs/2507.08738v2)]

## License

This repository is released under the **MIT License**. See [`LICENSE`](LICENSE).

## Contact

For questions, issues, or reproducibility concerns, please open a **GitHub Issue** or contact:

**Sherkhon Azimov**
[sherxonazimov94@pusan.ac.kr](mailto:sherxonazimov94@pusan.ac.kr)



