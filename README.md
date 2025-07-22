# 📈 Muon vs AdamW: Optimizer Scaling Dynamics in Transformer Training

🚀 **TL;DR**: Muon optimizer demolishes AdamW at scale! 94.6% vs 28.4% accuracy on large models 🔥  
⚡ **4-5% compute overhead** for **233% performance boost** 📊  
🧠 **Gradient orthogonalization** = game changer for LLM training 🎯  

![Learning Rate Sensitivity Analysis](results/experiment_1_learning_rate/lr_sensitivity_analysis.png)
*AdamW (blue) has sharp peaks, Muon (red) shows broader stability across learning rates*

![Performance Scaling Comparison](results/experiment_2_model_size/final_performance_comparison.png)  
*The dramatic divergence: Muon scales beautifully while AdamW crashes at 108M parameters*

![Training Dynamics](results/experiment_2_model_size/training_curves_with_uncertainty.png)
*Training curves reveal AdamW's catastrophic failure vs Muon's smooth convergence*

## 🎯 Key Findings

- 🔴 **Muon wins at scale**: 233% better accuracy on 108M parameter models
- 🟦 **AdamW dominates small models** but fails catastrophically at scale  
- ⚙️ **Only 4-5% compute overhead** for Muon's orthogonalization magic
- 📈 **Broader learning rate stability** makes Muon more robust
- 💡 **Gradient conditioning** becomes critical as models grow

## 🚀 Run the Experiments

### Option 1: Google Colab (Free Tier)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/vukrosic/muon-vs-adamw-scaling-dynamics/blob/main/muon_vs_adamw_for_llms.ipynb)

**Note**: Free Colab may require smaller model sizes. Use AI to adjust the code if needed!

### Option 2: Download & Run Locally
```bash
# Download the notebook
wget https://raw.githubusercontent.com/vukrosic/muon-vs-adamw-scaling-dynamics/main/muon_vs_adamw_for_llms.ipynb

# Or just download: muon_vs_adamw_for_llms.ipynb
# Then run in Jupyter/Colab
```

### Option 3: High-Performance Training (Recommended)
For the **full 108M parameter experiment**, I used [**Novita AI**](https://novita.ai/?ref=mjqyndm&utm_source=affiliate) with RTX 4090 - **4x faster** than free Colab! 

🎁 **You lose nothing, I get 10% commission to support more research like this!** 

The notebook has two experiments:
1. **Learning Rate Search** (runs on free Colab)
2. **Scaling Analysis** (needs more power - 4090 recommended)

## 📄 Full Paper

This repository contains the complete LaTeX source for our empirical study:

**"Scaling Dynamics of Muon versus AdamW: An Empirical Analysis of Optimizer Performance in Transformer Language Models"**

> **Authors**: Vuk Rosić (Óbuda University), Claude (Anthropic)  
> **Date**: July 21, 2025

## 🧪 Methodology

- **4 Model Sizes**: 11M → 29M → 50M → 108M parameters
- **Dataset**: SmolLM-Corpus (500k tokens)
- **Architecture**: Decoder-only Transformers with RoPE, RMSNorm, SwiGLU
- **Statistical Rigor**: Multiple seeds, t-tests for significance

## 📊 Results Summary

| Model Size | AdamW Accuracy | Muon Accuracy | Improvement |
|------------|---------------|---------------|-------------|
| 11M        | 79.4%         | 78.4%         | -1.3% ❌    |
| 29M        | 95.0%         | **96.3%**     | +1.4% ✅    |
| 50M        | 91.7%         | **96.1%**     | +4.8% ✅    |
| 108M       | **28.4%** 💥  | **94.6%** 🚀  | **+233%** 🔥 |

## 📂 Repository Structure

```bash
.
├── muon_vs_adamw_for_llms.ipynb    # 🚀 Main experiment notebook
├── results/                        # 📈 All plots and figures
│   ├── experiment_1_learning_rate/
│   └── experiment_2_model_size/
├── main.tex                       # 📄 Full LaTeX paper
└── README.md                      # 📖 You're here!
```

## 🔬 Key Insights

1. **Scale-Dependent Performance**: Optimizer choice becomes critical as models grow
2. **Gradient Orthogonalization**: Newton-Schulz iteration prevents destructive interference
3. **Learning Rate Robustness**: Muon tolerates broader hyperparameter ranges
4. **Computational Trade-off**: 4% overhead for 233% performance gain = no-brainer

## 📚 Citation

```bibtex
@article{rosic2025muon,
  title={Scaling Dynamics of Muon versus AdamW: An Empirical Analysis of Optimizer Performance in Transformer Language Models},
  author={Rosić, Vuk and Claude},
  journal={arXiv preprint},
  year={2025}
}
```

## 🤝 Support This Research

If this work helps you, consider:
- ⭐ **Star this repo**
- 🔄 **Share with your ML community** 
- ☕ **Use my [Novita AI link](https://novita.ai/?ref=mjqyndm&utm_source=affiliate)** for GPU training (supports more research!)

## 📬 Contact

Questions? Collaborations? Reach out!

**Vuk Rosić** – [vukrosic1@gmail.com](mailto:vukrosic1@gmail.com)

---
*Revolutionizing LLM training, one optimizer at a time* 🚀