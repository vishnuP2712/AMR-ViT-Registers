# AMR-ViT: Adaptive Multi-Register Vision Transformer

AMR-ViT is an adaptive Vision Transformer architecture that introduces **dynamically gated register tokens** to adjust representational capacity based on input complexity, improving both **performance** and **interpretability** across medical and natural image domains.

---

## 📌 Overview

Conventional Vision Transformers rely on a **fixed token structure**, which limits their ability to adapt to inputs of varying complexity.  
This limitation is particularly critical in **medical imaging**, where subtle visual patterns demand richer contextual reasoning.

**AMR-ViT (Adaptive Multi-Register Vision Transformer)** addresses this challenge by introducing:

- A bank of **learnable register tokens**
- A **gating controller** that dynamically activates registers for each input image

This enables **input-aware computation**, improving accuracy and interpretability while maintaining computational efficiency.

---

## ✨ Key Features

### 🔀 Adaptive Register Tokens (0–8 Registers)
- Registers are dynamically activated based on image complexity.

### 🎛️ Gating Controller
- Learns to predict register activation from global image context.

### 📈 Performance Improvement
- Achieves a **+3.78% accuracy gain** over a standard ViT baseline on **CIFAR-10**.

### 🧠 Interpretability
- Attention maps and register activations provide insight into model decision-making.

### ⚙️ Lightweight Design
- Minimal increase in parameters and FLOPs compared to baseline ViT.

---

## 🧠 Architecture

### AMR-ViT Processing Pipeline

Input Image
↓
Patch Embedding
↓
Global Context Extraction
↓
Gating Controller
↓
Adaptive Register Activation
↓
Transformer Encoder Stack
↓
Classification Head


### Conceptual Flow

1. Input images are converted into patch embeddings.
2. A global descriptor summarizes the image content.
3. A gating network predicts activation weights for register tokens.
4. Activated registers are injected into the token sequence.
5. Transformer encoders refine representations for final classification.

---

## 📊 Experimental Results

| Model            | Test Accuracy | Register Usage |
|------------------|---------------|----------------|
| Standard ViT     | 63.97%        | Fixed (0)     |
| **AMR-ViT (Ours)** | **67.75%**    | 0–8 (Dynamic) |

---

## 🔍 Interpretability Insights

- Simple images activate **fewer registers (1–2)**
- Complex images activate **more registers (6–8)**
- Attention maps demonstrate stronger focus on task-relevant regions
- For **ChestMNIST**, attention aligns with clinically meaningful lung regions

---

## 📁 Repository Structure
```bibtex
Adaptive-ViT-Registers/
│
├── AMR_ViT.ipynb        # Training, evaluation, and visualization
├── SETUP_GUIDE.md      # Environment setup instructions
├── requirements.txt    # Python dependencies
├── AMR-ViT_Report.pdf  # Project report / research paper
├── LICENSE             # License information
└── README.md           # Project documentation
```
---

## 🧰 Installation

```bibtex
git clone https://github.com/vineethk297/Adaptive-ViT-Registers.git
cd Adaptive-ViT-Registers
pip install -r requirements.txt
```

---

## 📜 Citation

```bibtex
@article{amrvit2024,
  title={Adaptive Multi-Register Vision Transformer for Medical and Natural Image Classification},
  author={Kamkolam, Sai Prasanna and Pappula, Vishnu Vardhan Reddy and Mamidipally, Vineeth Kumar},
  year={2024},
  institution={Florida Atlantic University}
}

---
```
## 📄 License

This project is licensed under the MIT License.  
See the LICENSE file for more details.

