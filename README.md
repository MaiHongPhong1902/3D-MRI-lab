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
Dưới đây là phần **tóm tắt README** bạn có thể thêm vào phần đầu của dự án GitHub để giới thiệu ngắn gọn về **SepU-Net** và nội dung chính:

---

# SepU-Net: Lightweight MRI Brain Tumor Segmentation Model

**SepU-Net** is a lightweight and efficient deep learning architecture designed for **brain tumor segmentation** from MRI scans. By integrating **Depthwise Separable Convolutions** and **Pointwise Convolutions** into the classic U-Net, SepU-Net significantly reduces computational complexity while maintaining high segmentation accuracy.

### 🔍 Highlights:

* 📉 **82% reduction in parameters** vs. original U-Net (1.38M vs. 7.76M).
* 🧠 Trained on **BraTS2020** dataset for multi-class tumor segmentation.
* 🎯 Achieved Dice Scores:

  * Necrotic Core: **0.8652**
  * Edema: **0.7602**
  * Enhancing Tumor: **0.8213**
* ⚡ Requires only **7 GFLOPs** and **1.2GB** memory, suitable for real-time and embedded systems.
* 🧪 Includes full pipeline: preprocessing (NiBabel), training, evaluation, and result visualization.

### 📁 Repository Contents

* `data_preprocessing/`: Scripts to convert 3D MRI (NIfTI) to 2D slices.
* `models/`: Implementation of SepU-Net with separable convolution blocks.
* `training/`: Training and evaluation scripts with early stopping, cosine LR scheduling.
* `results/`: Visual segmentation outputs and logs.

### 📜 Citation

If you use SepU-Net in your research, please cite:

> Mai Hong Phong, Lam Mai Thanh, Nguyen Ngo Lam. *SepU-Net: MRI Segmentation Algorithm Using Depthwise Separable Convolution and Pointwise Convolution Integrated U-Net*, Journal of Technical Education Science, HCMUTE, 2025.

---


## Requirements  
- Python 3.8+, TensorFlow 2.9+  
- Full dependencies: `requirements.txt`  

