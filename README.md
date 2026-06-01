# DIINA-CodeSwitching-
Official implementation of DIINA: A neural architecture with Dynamic Inhibitory Regulation for stabilizing multilingual code-switching and reducing lexical interference. ‌
markdown
# DIINA: Dynamic Inhibitory Interface for Neural Architectures
‌
**Official implementation of DIINA: A neural architecture with Dynamic Inhibitory Regulation for stabilizing multilingual code-switching and reducing lexical interference.**
‌
---
‌
## 🌟 Overview
DIINA is a specialized neural architecture designed to address the challenges of **Code-Switching** and **Semantic Leakage** in multilingual models. Unlike standard transformers, DIINA introduces a biological-inspired inhibitory mechanism that adaptively suppresses non-target language activation.
‌
### Key Innovations:
- **Dynamic Inhibitory Regulator (DIR):** Estimates the degree of non-target activation.
- **Inhibition-Augmented Attention:** Modulates attention scores to ensure target-language stability.
- **Treasure Corpus:** A curated multilingual dataset (EN, FA, TR, AZ) for evaluating complex switching patterns.
‌
---
‌
## 📐 Mathematical Foundation (Appendix C)
‌
The core of DIINA lies in its modified attention mechanism:
‌
### 1. Inhibitory Signal Calculation
The DIR module computes the inhibitory strength ($w_{\mathrm{inh}}$) based on hidden states ($H$) and contextual cues ($C$):
$$w_{\mathrm{inh}} = \sigma(W_{\mathrm{inh}}[H; C] + b_{\mathrm{inh}})$$
‌
### 2. Augmented Attention
This signal is integrated into the attention mechanism as an inhibitory bias ($B_{\mathrm{inh}}$):
$$\mathrm{Att}_{\mathrm{inh}}(Q, K, V, w_{\mathrm{inh}}) = \operatorname{softmax}\left(\frac{QK^T}{\sqrt{d_k}} + B_{\mathrm{inh}}\right)V$$
‌
---
‌
## 📊 Evaluation & Results
DIINA shows significant robustness in **Intra-sentential Code-Switching**, where lexical competition is strongest.
‌
### Error Profile Mitigation:
- ✅ Reduces unintended lexical substitutions.
- ✅ Fixes delayed adaptation after switch points.
- ✅ Eliminates mixed-language phrases that reduce semantic precision.
‌
---
‌
## 🛠 Project Structure
- `models/`: PyTorch implementation of DIR and Attention layers.
- `data/`: Sample switching patterns from the Treasure Corpus.
- `paper/`: Supplementary materials and architectural details.
‌
---
‌
## ✍️ Citation
If you use DIINA in your research, please cite:bibtex
@article{pegah2026diina,
title={DIINA: Dynamic Inhibitory Interface for Neural Architectures},
author={Dr. Pegah},
year={2026}
}
