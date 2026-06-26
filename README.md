![Python](https://img.shields.io/badge/Python-3.12-blue) ![PyTorch](https://img.shields.io/badge/PyTorch-2.x-red) ![Google Colab](https://img.shields.io/badge/Google%20Colab-Notebook-orange) ![License](https://img.shields.io/badge/License-MIT-green)
# Wildfire_Segmentation_Comparison
A deep learning-based wildfire monitoring framework for semantic segmentation, wildfire region analysis, fire severity assessment, and comparative evaluation of multiple segmentation models using the FLAME dataset.

## 📌 Project Overview
Wildfires pose significant environmental and economic threats, making early detection and accurate monitoring essential. This project develops an intelligent wildfire monitoring framework that automatically identifies wildfire regions from aerial imagery using deep learning semantic segmentation.

The study compares three state-of-the-art segmentation models:
- U-Net
- Attention U-Net
- DeepLabV3+

The segmented wildfire regions are further analyzed to estimate the fire-affected area and classify wildfire severity into different risk levels.

Based on experimental evaluation, the best-performing model is selected for future development toward real-world wildfire monitoring applications.

## 🎯 Objectives
- Perform wildfire semantic segmentation using deep learning.
- Compare U-Net, Attention U-Net, and DeepLabV3+.
- Evaluate model performance using Dice Score and IoU.
- Estimate fire-affected area from segmented wildfire masks.
- Classify wildfire severity into Low, Moderate, and High Risk.
- Identify the most suitable segmentation model for future wildfire monitoring systems.

## Key Features
- Wildfire semantic segmentation
- Comparison of three deep learning models
- Fire severity estimation
- Pixel-wise burned area analysis
- Risk level classification
- Comparative evaluation using Dice Score and IoU

## 📂 Dataset
Dataset Used:
**FLAME (Fire Luminosity Airborne-based Machine Learning Evaluation) Dataset**
The dataset contains UAV-based wildfire RGB images along with pixel-level segmentation masks for wildfire detection and semantic segmentation.

Dataset includes:
- RGB wildfire images
- Ground truth segmentation masks
- Training images
- Testing images

Dataset Link:
https://ieee-dataport.org/open-access/flame-dataset-aerial-imagery-pile-burn-detection-using-drones-uavs

## 🧠 Deep Learning Models
### 1. U-Net
U-Net is a convolutional neural network specifically designed for image segmentation. It consists of an encoder-decoder architecture with skip connections that preserve spatial information, making it highly effective for pixel-level segmentation tasks.

**Advantages**
- Fast training
- Simple architecture
- Effective on small datasets

### 2. Attention U-Net
Attention U-Net extends the original U-Net by incorporating Attention Gates, allowing the network to focus on important wildfire regions while suppressing irrelevant background information.

**Advantages**
- Better feature localization
- Improved segmentation accuracy
- Reduces false positives

### 3. DeepLabV3+
DeepLabV3+ combines Atrous Spatial Pyramid Pooling (ASPP) with an encoder-decoder architecture to capture multi-scale contextual information while preserving object boundaries.

**Advantages**
- Excellent multi-scale feature extraction
- Better boundary segmentation
- Higher segmentation accuracy
- Selected as the best-performing model in this study

## 🔄 Project Workflow
1. Input wildfire RGB image
2. Image preprocessing
3. Semantic segmentation using:
   - U-Net
   - Attention U-Net
   - DeepLabV3+
4. Generate wildfire segmentation mask
5. Fire region analysis
6. Fire severity estimation
7. Risk level classification
8. Comparative performance evaluation

## 📁 Repository Structure
```
Deep-Learning-Wildfire-Monitoring/
│
├── notebooks/
│   └── Wildfire_Monitoring.ipynb
│
├── models/
│   ├── unet_best.pth
│   ├── attention_unet_best.pth
│   └── deeplabv3_best.pth
│
├── datasets/
│
├── outputs/
│
├── README.md
├── requirements.txt
└── LICENSE
```

## ⚙️ Installation

### Clone the repository
```bash
git clone https://github.com/yourusername/Deep-Learning-Wildfire-Monitoring.git
```
### Install the required packages
```bash
pip install -r requirements.txt
```
### Download the Dataset
Download the FLAME dataset from:
https://ieee-dataport.org/open-access/flame-dataset-aerial-imagery-pile-burn-detection-using-drones-uavs

Place the dataset in the appropriate directory as described in the notebook.

### Run the Project
Open the notebook in **Google Colab** or any compatible Python environment, update the dataset paths if required, and run all cells sequentially.

## 📊 Experimental Results
The three deep learning models were trained and evaluated using the FLAME wildfire dataset. Model performance was assessed using standard semantic segmentation metrics, including Dice Score and Intersection over Union (IoU).

The generated wildfire masks were further analyzed to estimate fire-affected regions and classify wildfire severity into different risk levels.

## 🏆 Model Comparison
| Model | Dice Score | IoU Score | Overall Performance |
|-------|-----------:|----------:|--------------------|
| U-Net | 0.6500 | 0.4830 | Good Baseline |
| Attention U-Net | 0.6287 | 0.4603 | Good |
| **DeepLabV3+** | **0.7332** | **0.5810** | ⭐ Best |

### Key Findings
- DeepLabV3+ achieved the highest Dice Score (**0.7332**) and IoU Score (**0.5810**), demonstrating superior wildfire segmentation performance.
- U-Net provided competitive results and served as a strong baseline model.
- Attention U-Net produced comparable segmentation results but slightly underperformed compared to U-Net and DeepLabV3+ on the FLAME dataset.
- DeepLabV3+ effectively captured multi-scale contextual information and generated more accurate wildfire boundaries, making it the most suitable model for the proposed wildfire monitoring framework.

## 🔍 Fire Severity Assessment
The predicted wildfire segmentation masks were used to estimate the percentage of fire-affected pixels in each image.

Based on the estimated fire percentage, wildfire severity was categorized into three risk levels:
| Fire Percentage | Risk Level |
|----------------:|-----------|
| < 1% | Low Risk |
| 1% – 5% | Moderate Risk |
| > 5% | High Risk |

This analysis demonstrates how semantic segmentation outputs can be transformed into meaningful information for wildfire monitoring and decision support.

## 🎯 Conclusion
This project successfully developed a deep learning-based wildfire monitoring framework using semantic segmentation techniques.

Three state-of-the-art segmentation models—U-Net, Attention U-Net, and DeepLabV3+—were implemented and evaluated on the FLAME dataset. Based on Dice Score, IoU Score, qualitative prediction results, and wildfire severity analysis, DeepLabV3+ achieved the best overall performance.

The proposed framework not only performs wildfire segmentation but also estimates fire-affected regions and classifies wildfire severity, making it suitable for future wildfire monitoring and disaster management applications.

## 🚀 Future Work
The following extensions were identified from recent wildfire research literature:
| Future Scope | Inspired From |
|--------------|---------------|
| Fire Severity Assessment and Risk Mapping | Land8Fire (2025) |
| Explainable AI (XAI) for Wildfire Segmentation | Land8Fire (2025) |
| Lightweight Real-Time Deployment on UAVs and Edge Devices | Lightweight DeepLabV3+ Burned Area Identification |

## 🌍 Real-World Applications
Although this project focuses on wildfire monitoring, the proposed segmentation and analysis framework can be adapted to several other environmental and disaster management applications.
| Application | Description |
|------------|-------------|
| Wildfire Monitoring | Detect wildfire regions, estimate burned area, and assess fire severity. |
| Burned Area Mapping | Identify post-fire damaged regions for ecological assessment and recovery planning. |
| Deforestation Monitoring | Detect forest loss and monitor illegal logging using aerial or satellite imagery. |
| Illegal Waste Dump Detection | Segment waste dumping areas from UAV imagery for environmental monitoring. |
| Oil Spill Detection | Identify oil-contaminated regions in aerial or satellite images for marine disaster management. |
| Flood Mapping | Segment flood-affected regions for rapid disaster response and damage assessment. |
| Landslide Detection | Detect landslide-affected regions for hazard mapping and infrastructure planning. |

## 📚 References
This project is inspired by the following research works:
1. FireCast-Fusion: Physics-Guided Fusion of UAV RGB–Thermal Imagery and Environmental Data for Near-Term Wildfire Spread Prediction
2. Land8Fire: A Benchmark Dataset for Forest Fire Semantic Segmentation
3. A Lightweight DeepLabV3+ Network Integrating Deep Transitive Transfer Learning and Attention Mechanism for Burned Area Identification
4. Real-time Deforestation Anomaly Detection using YOLO and LangChain Agents for Sustainable Environmental Monitoring

## 🙏 Acknowledgements
- FLAME Dataset
- PyTorch
- Torchvision
- Google Colab
- OpenCV
- NumPy
- Matplotlib

## Project Status
Current Stage
- U-Net Completed
- Attention U-Net Completed
- DeepLabV3+ Completed
- Model Comparison Completed
- Fire Severity Assessment Completed
- Future Work Analysis Completed

Next Phase
- Wildfire Spread Prediction
- Explainable AI
- Risk Mapping

## 📄 License
This project is developed for academic and research purposes.

## 📷 Sample Results
### Model Comparison
<p align="center">
<img src="Wildfire_Monitoring/outputs/model-comparison.png" width="900">
</p>

### Fire Severity Assessment
<p align="center">
<img src="Wildfire_Monitoring/outputs/fire-severity.png" width="700">
</p>

