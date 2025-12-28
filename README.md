# PRISM: Pay Attention Later


# ⚠️ ARCHITECTURAL UPDATE NOTICE (v2 vs v1)

**Current Status: The code in this repository implements PRISM v2 (RoSE - Rotary Semantic Embeddings).**

The original preprint (*arXiv:2512.01208v1*) described a preliminary version of the harmonic embedding mechanism which has since been superseded. The code here reflects the corrected "Semantic RoSE" architecture, which resolves the phase-locking flaws identified in the initial definitions.

* **For the v2 updates:** See the archived release DOI: [10.5281/zenodo.17330341](https://doi.org/10.5281/zenodo.17330341).
* **For the working, state-of-the-art implementation:** Use the `.ipynb` files in this main branch.

**We strongly recommend using the current repository code for reproduction efforts as it contains critical stability fixes for the spectral gating mechanism.**




---

### Official Implementation for arXiv:2512.01208
This repository contains the experimental code for **PRISM** (Phase-Resonant Intelligent Spectral Model)...
**Official Implementation for arXiv:2512.01208**

This repository contains the experimental code for **PRISM** (Phase-Resonant Intelligent Spectral Model) and the **ISMR** (Iterative Semantic Map Refinement) diagnostic protocol.

All notebooks were created and executed using Google Colab.

## 📂 1. The Marathon (General Training)
*Training the models from scratch on WMT14/Multi30k to measure general competence.*
* **`PRISM_train.ipynb`** - Main training script for the PRISM architecture ($O(N \log N)$ Harmonic Convolutions).
* **`AIAYN_Baseline_Training.ipynb`** - Training script for the Standard Transformer Baseline ("Attention Is All You Need").
* **`Train_With_Helsinki_Pretrained_Embeddings.ipynb`** - Control experiment using external pre-trained embeddings to verify initialization gains.

## 📂 2. The Sprint (Few-Shot Plasticity)
*Fine-tuning pre-trained models on 5 novel concepts (e.g., "Schmerzhotel") to test plasticity vs. forgetting.*
* **`PRISM_few_shot_experiment.ipynb`** - PRISM "Sprint" protocol (High acquisition, negligible forgetting).
* **`Baseline_few_shot_experiment_py.ipynb`** - Transformer Baseline "Sprint" protocol (Demonstrates catastrophic forgetting).

## 📂 3. ISMR Diagnostic (The "Tax")
*The "Iterative Semantic Map Refinement" protocol used to diagnose the Semantic Alignment Tax.*
* **`Iterative_trainer_v2.ipynb`** - (Latest) Implementation of the ISMR pipeline (Train Iter 1 $\to$ Extract Map $\to$ Train Iter 2).
* **`Iterative_Trainer.ipynb`** - (Legacy) Earlier version of the ISMR trainer.
* **`ISMR_test_results.ipynb`** - Visualization and analysis of the learning curves (e.g., the "20-layer vs 1-layer" comparison).
* **`Ablation_Study_v2.ipynb`** - (Latest) Geometric vs. Statistical ablation studies (Shuffled Maps).
* **`Ablation_Study.ipynb`** - (Legacy) Initial ablation experiments.

## 📂 4. Data Processing
* **`Multi30k_data_processing.ipynb`** - Pre-processing scripts for the Multi30k dataset used in the diagnostic phase.
* **`Multi3k_data_processing.ipynb`** - (Legacy) Alternate processing script.

WMT14 uses same data processing pipeline. Already processed huggingface datasets are already selected on code. 

---
**Citation:**
```bibtex
@misc{yildirim2025payattentionlater,
      title={Pay Attention Later: From Vector Space Diffusion to Linearithmic Spectral Phase-Locking}, 
      author={Alper Yıldırım and İbrahim Yücedağ},
      year={2025},
      eprint={2512.01208},
      archivePrefix={arXiv},
      primaryClass={cs.LG}
}
