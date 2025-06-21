# SepU-Net: Lightweight Brain Tumor Segmentation  
Official implementation of the paper:  
"[Paper Title]" (DOI: 10.xxxx/yyyy)  

| **Hyperparameter**        | **Value**                  | **Validation / Notes**                                    |
| ------------------------- | -------------------------- | --------------------------------------------------------- |
| **Optimizer**             | Adam                       | Momentum β₁=0.9, β₂=0.999                                 |
| **Initial Learning Rate** | 0.001                      | Cosine decay schedule over 35 epochs                      |
| **Batch Size**            | 16                         | Tested range: 8–32                                        |
| **Loss Function**         | Dice + Cross-Entropy       | Weighted 0.7:0.3                                          |
| **Input Resolution**      | 128 × 128 (2D axial slice) | Resampled from original 150×128×128                       |
| **Data Augmentation**     | Rotation (±15°), Flip      | Intensity scaling (±20%)                                  |
| **Dropout Rate**          | 0.2                        | Applied after each separable convolution layer            |
| **Early Stopping**        | Patience = 10              | Monitored on validation Dice score for ET (val\_Dice\_ET) |

## Requirements  
- Python 3.8+, TensorFlow 2.9+  
- Full dependencies: `requirements.txt`  

