# 📈 Muon vs AdamW: Optimizer Scaling Dynamics in Transformer Training



This repository contains the full LaTeX source for our empirical study:

**Scaling Dynamics of Muon versus AdamW: An Empirical Analysis of Optimizer Performance in Transformer Language Models**

> **Authors**: Vuk Rosić (Óbuda University), Claude (Anthropic)  
> **Date**: July 21, 2025

## 🧠 Overview

Optimizer choice critically impacts large language model (LLM) training. While **AdamW** remains the default in transformer-based architectures, **Muon**—a newer optimizer incorporating **gradient orthogonalization via Newton-Schulz iteration**—shows promise for improved convergence at scale.

This study compares **AdamW** and **Muon** across four model sizes (11M to 108M parameters) trained on the **SmolLM-Corpus**. Results show:

- 🟦 **AdamW** outperforms on small models  
- 🔴 **Muon** scales better, outperforming AdamW dramatically on large models  
- 💥 **AdamW catastrophically fails** at 108M parameters  
- ⚙️ **Muon incurs only 4–5% compute overhead**

## 📄 Paper Highlights

- 📊 **Learning Rate Sweeps** show Muon is more stable
- 🚀 **Scaling Analysis** reveals divergence at 108M scale
- 🧮 **Gradient Orthogonalization** improves training stability
- 💡 **Practical Implications** for choosing optimizers in LLM training

## 📂 Contents

```bash
.
├── results/                      # Plots and figures used in the paper
│   ├── experiment_1_learning_rate/
│   └── experiment_2_model_size/
├── main.tex                     # Full LaTeX source of the paper
├── references.bib               # Bibliography entries (if split)
├── README.md                    # You're here!
````

## 📸 Key Figures

* 🔍 **Learning Rate Sensitivity**: AdamW peaks sharply, Muon is broader
* 📈 **Training Curves**: AdamW flattens early at large scale; Muon improves steadily
* 🧪 **Validation Accuracy**: Muon reaches **94.6%** on 108M model vs **28.4%** for AdamW
* ⏱️ **Compute Overhead**: \~4.2% for Muon

## 📚 Citation

If you use or refer to this work, please cite:

```bibtex
@article{rosic2025muon,
  title={Scaling Dynamics of Muon versus AdamW: An Empirical Analysis of Optimizer Performance in Transformer Language Models},
  author={Rosić, Vuk and Claude},
  journal={arXiv preprint},
  year={2025}
}
```

## 🧪 Reproducibility Notes

* Dataset: SmolLM-Corpus (500k tokens)
* Hardware: T4 GPU (limited scale)
* Framework: PyTorch + custom optimizer
* Training length varies by model size to equalize compute

## 📬 Contact

For questions or collaborations, feel free to reach out:

* Vuk Rosić – [vukrosic1@gmail.com](mailto:vukrosic1@gmail.com)