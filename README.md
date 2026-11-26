# Autoencoder-Assisted CNN for Distorted Satellite Image Classification

**Improving classification accuracy under unseen Gaussian blur from 61.14% to 80.12% (+18.98 percentage points).**

## Overview

Image classifiers trained on clean data can become unreliable when the input distribution changes. This project investigates whether autoencoder-assisted training can make a CNN more robust to image distortions without increasing the size of the classifier.

The experiment uses EuroSAT satellite imagery and compares a conventional CNN with the same CNN architecture trained on autoencoder-reconstructed images. Gaussian blur is introduced only at test time, allowing the experiment to examine generalization to a distortion not encountered during training.

## Experimental design

| Component | Configuration |
| --- | --- |
| Dataset | EuroSAT satellite imagery |
| Baseline | Standard CNN trained on clean images |
| Proposed approach | Same CNN architecture trained on autoencoder-reconstructed images |
| Training condition | Clean source images only |
| Test conditions | Clean images and previously unseen Gaussian-blurred images |
| Evaluation | Classification accuracy and F1 score |

## Results

| Metric | Baseline CNN | Autoencoder-assisted CNN | Change |
| --- | ---: | ---: | ---: |
| Clean-image accuracy | 92.12% | 88.69% | -3.43 pp |
| Gaussian-blur accuracy | 61.14% | **80.12%** | **+18.98 pp** |
| Gaussian-blur F1 score | 59.85% | **80.05%** | **+20.20 pp** |

The baseline performs better on clean images, but the autoencoder-assisted approach retains substantially more accuracy under the unseen blur condition. This illustrates a trade-off between clean-image performance and robustness rather than an improvement across every condition.

## Tools and technologies

- Python, PyTorch and TorchVision
- scikit-learn for evaluation
- Pandas and Matplotlib for analysis and visualization

## Reproducing the experiment

1. Obtain the EuroSAT dataset and prepare a Python environment with the libraries used by the experiment.
2. Train the autoencoder using clean source images and generate reconstructed training inputs.
3. Train the baseline and autoencoder-assisted CNNs using their respective inputs, keeping the classifier architecture consistent.
4. Evaluate both approaches on clean test images and the Gaussian-blur test condition.
5. Compare accuracy and F1 scores using the same test split and evaluation protocol.

## Limitations

The reported results concern a particular unseen distortion and experimental setup. They do not establish robustness to every type or severity of corruption. Further evaluation across different distortions, datasets and architectures would help establish how broadly the approach generalizes.

## Project links

- [Project overview and demonstration](https://morsalin-antor-portfolio.vercel.app/project_info.html?name=ae_cnn)
- [GitHub profile](https://github.com/antor-morsalin)
