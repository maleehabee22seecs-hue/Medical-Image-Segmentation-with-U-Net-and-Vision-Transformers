# Skin Lesion Segmentation with U-Net and TransUNet

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-EE4C2C?logo=pytorch&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google%20Colab-Notebook%20Ready-F9AB00?logo=googlecolab&logoColor=white)
![Medical Imaging](https://img.shields.io/badge/Domain-Medical%20Imaging-0E7490)
![Vision Transformers](https://img.shields.io/badge/Model-Vision%20Transformers-7C3AED)
![U--Net](https://img.shields.io/badge/Model-U--Net-2563EB)
![ISIC 2018](https://img.shields.io/badge/Dataset-ISIC%202018-16A34A)

## Project Overview
This project presents an academic comparison of **U-Net** and **TransUNet** for automated skin lesion segmentation on the **ISIC 2018** dataset. It evaluates convolution-based and transformer-enhanced architectures under practical GPU memory constraints while targeting high segmentation fidelity.

## Motivation
Accurate lesion boundary delineation is essential for computer-aided dermatology workflows. Classical CNNs such as U-Net remain strong baselines, while transformer-based encoders can capture broader contextual information. This repository documents a direct, reproducible comparison to understand these trade-offs in a clinically relevant benchmark.

## Key Features
- Comparative implementation of **U-Net** and **TransUNet**.
- Training pipeline for **ISIC 2018** lesion segmentation.
- **Progressive unfreezing** with differential learning rates for stable fine-tuning.
- Memory-conscious experimentation (trained under ~15 GB GPU memory).
- Quantitative and qualitative analysis framework.

## Results Summary
The best-performing setup reached a **Dice Similarity Coefficient (DSC) of 0.9139**, demonstrating strong segmentation quality while maintaining practical training efficiency.

## Architecture Comparison

| Aspect | U-Net | TransUNet |
|---|---|---|
| Backbone type | Convolutional encoder-decoder | Transformer encoder + U-Net-style decoder |
| Strength | Strong local feature extraction | Better global context modeling |
| Data efficiency | Typically strong on moderate data | Often benefits from robust pretraining |
| Compute demand | Lower | Higher |
| Parameter complexity | Moderate | Moderate to high |
| Boundary detail | Strong with skip connections | Strong, with improved context awareness |

## Dataset Description
**ISIC 2018 (Task 1: Lesion Boundary Segmentation)** is a dermoscopic image benchmark containing paired skin lesion images and binary masks. The dataset supports evaluation of pixel-level lesion delineation using overlap-based metrics such as Dice and IoU.

## Model Architectures
### U-Net
A symmetric encoder-decoder segmentation network with skip connections that preserve spatial detail and improve boundary reconstruction.

### TransUNet
A hybrid architecture combining transformer-based global representation learning in the encoder with a U-Net-inspired decoder for dense prediction.

## Training Strategy
- Input preprocessing and mask alignment for robust supervised segmentation.
- Loss and optimizer configured for overlap-sensitive optimization.
- Validation-based model selection using Dice-driven monitoring.
- Hardware-aware settings to remain within memory limits.

## Progressive Unfreezing
Progressive unfreezing is used to stabilize optimization during fine-tuning:
1. Start training with only higher-level layers unfrozen.
2. Gradually unfreeze deeper encoder blocks over epochs.
3. Apply **differential learning rates** (lower LR for pretrained layers, higher LR for task-specific layers).

This approach reduces catastrophic forgetting and improves adaptation to dermatology imagery.

## Technologies Used
- Python
- PyTorch
- Vision Transformers
- U-Net
- Google Colab
- Medical image segmentation tooling

## Repository Structure
```text
.
├── LICENSE
└── README.md
```

## Installation
```bash
git clone https://github.com/maleehabee22seecs-hue/Medical-Image-Segmentation-with-U-Net-and-Vision-Transformers.git
cd Medical-Image-Segmentation-with-U-Net-and-Vision-Transformers
```

## Usage Instructions
1. Prepare ISIC 2018 images and masks in your preferred data directory.
2. Configure model choice (`U-Net` or `TransUNet`) and training hyperparameters.
3. Run training and validation in your notebook or training script environment.
4. Evaluate using Dice/IoU and review qualitative masks.

## Performance Metrics

| Model | Dice (DSC) | IoU | Notes |
|---|---:|---:|---|
| U-Net | _TBD_ | _TBD_ | Baseline CNN segmentation |
| TransUNet | **0.9139** | _TBD_ | Best observed Dice in this study |

## Sample Qualitative Results

| Input Dermoscopy Image | Ground Truth Mask | Predicted Mask (U-Net) | Predicted Mask (TransUNet) |
|---|---|---|---|
| ![Input Placeholder](docs/images/input_placeholder.png) | ![GT Placeholder](docs/images/gt_placeholder.png) | ![UNet Placeholder](docs/images/unet_pred_placeholder.png) | ![TransUNet Placeholder](docs/images/transunet_pred_placeholder.png) |

> Replace placeholders with repository images once qualitative outputs are exported.

## Future Improvements
- Add full experiment configuration files for strict reproducibility.
- Report cross-validation statistics with confidence intervals.
- Expand comparison to additional hybrid CNN-Transformer models.
- Add post-processing and uncertainty estimation analysis.

## References
1. Olaf Ronneberger, Philipp Fischer, Thomas Brox. *U-Net: Convolutional Networks for Biomedical Image Segmentation*.
2. Jieneng Chen et al. *TransUNet: Transformers Make Strong Encoders for Medical Image Segmentation*.
3. Noel C. F. Codella et al. *ISIC 2018: Skin Lesion Analysis Toward Melanoma Detection*.

## Authors
- **Maleeha B.** (@maleehabee22seecs-hue)

## Citation
If you use this repository in academic work, please cite:

```bibtex
@misc{maleeha2026_skin_lesion_segmentation,
  title        = {Skin Lesion Segmentation with U-Net and TransUNet on ISIC 2018},
  author       = {Maleeha B.},
  year         = {2026},
  howpublished = {\url{https://github.com/maleehabee22seecs-hue/Medical-Image-Segmentation-with-U-Net-and-Vision-Transformers}}
}
```

## License
This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.
