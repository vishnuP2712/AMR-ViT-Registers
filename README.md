# AMR-ViT: Adaptive Multi-Register Vision Transformer

A novel Vision Transformer architecture featuring an adaptive register mechanism that dynamically adjusts based on input complexity, improving both efficiency and interpretability across medical and natural image datasets.

## 🎯 Key Features

- **Adaptive Register Bank**: Dynamic gating mechanism that selectively activates 0-8 register tokens based on image content
- **Cross-Domain Performance**: Tested on both medical imaging (ChestMNIST) and natural images (CIFAR-10)
- **Interpretability**: Built-in attention visualization for understanding model focus
- **Efficient Training**: Mixed precision training with AMP for faster convergence

## 📊 Results

| Metric | Standard ViT (Baseline) | AMR-ViT (Ours) | Improvement |
|--------|------------------------|----------------|-------------|
| CIFAR-10 Test Accuracy | Baseline | Enhanced | +X.XX% |
| Model Type | Static | Adaptive | - |
| Registers Used | 0 (Fixed) | 0-8 (Dynamic) | Flexible |

## 🏗️ Architecture

### Core Components

1. **FlexiblePatchEmbed**: Handles variable input resolutions (28×28 for medical, 32×32 for natural images)
2. **Adaptive Controller**: Neural network that generates gate weights for register selection
3. **Gated Register Bank**: Learnable tokens that are dynamically weighted per input
4. **InterpretableBlock**: Custom transformer layers with attention weight extraction

### Model Architecture

```
Input Image → Patch Embedding → [CLS Token + Adaptive Registers + Patches]
    ↓
Positional Encoding
    ↓
Transformer Blocks (with Attention Visualization)
    ↓
Layer Norm → Classification Head
```

## 📦 Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/amr-vit-project.git
cd amr-vit-project

# Install dependencies
pip install -r requirements.txt
```

## 🚀 Quick Start

### Training on MedMNIST (ChestMNIST)

```python
from amr_vit import AdaptiveRegisterViT
import torch

# Initialize model for medical imaging
model = AdaptiveRegisterViT(
    img_size=28,
    patch_size=4,
    in_chans=1,        # Grayscale
    num_classes=14,    # 14 diseases
    embed_dim=192,
    depth=12,
    num_heads=3,
    max_registers=8
)

# Training code available in AMR_ViT.ipynb
```

### Training on CIFAR-10

```python
# Initialize model for natural images
model = AdaptiveRegisterViT(
    img_size=32,
    patch_size=4,
    in_chans=3,        # RGB
    num_classes=10,
    embed_dim=128,
    depth=6,
    num_heads=4,
    max_registers=8
)
```

## 📓 Notebooks

- **`AMR_ViT.ipynb`**: Complete implementation with training, evaluation, and visualization
  - MedMNIST training and evaluation
  - CIFAR-10 experiments
  - Attention map visualization
  - Comparative analysis with baseline ViT

## 🔬 Experiments

### Dataset Support

1. **ChestMNIST** (MedMNIST)
   - 14-class multi-label classification
   - Grayscale chest X-rays (28×28)
   - Focus on artifact suppression and disease detection

2. **CIFAR-10**
   - 10-class single-label classification
   - RGB natural images (32×32)
   - Testing generalization across domains

### Visualization

The model provides interpretable attention maps showing:
- Which regions the model focuses on
- How register gates adapt to different inputs
- Comparison between healthy and pathological cases

## 🛠️ Requirements

- Python 3.8+
- PyTorch 1.12+
- torchvision
- medmnist
- numpy
- pandas
- matplotlib

See `requirements.txt` for complete dependencies.

## 📖 Usage Examples

### Attention Visualization

```python
from visualization import visualize_prediction

# Visualize attention on a specific sample
visualize_prediction(model, val_dataset, index=10)
```

### Model Evaluation

```python
from utils import evaluate_model

# Evaluate on test set
test_accuracy = evaluate_model(model, test_loader)
print(f"Test Accuracy: {test_accuracy:.2f}%")
```

## 🏆 Team Members

- **Sai Prasanna Kamkolam**
- **Vishnu Vardhan Reddy Pappula**
- **Vineeth Kumar Mamidipally**

## 📄 Project Structure

```
amr-vit-project/
├── AMR_ViT.ipynb          # Main notebook with all experiments
├── README.md              # This file
├── requirements.txt       # Python dependencies
├── LICENSE               # MIT License
└── .gitignore           # Git ignore rules
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- MedMNIST dataset creators
- PyTorch and torchvision teams
- Vision Transformer (ViT) paper authors

## 📧 Contact

For questions or collaborations, please open an issue or contact the team members.

---

⭐ If you find this project useful, please consider giving it a star!
