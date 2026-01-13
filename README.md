🧠 PIQED: Perception-Inspired Quantum Edge Detection

📌 Overview

PIQED (Perception-Inspired Quantum Edge Detection) is a lightweight and resource-efficient quantum image edge detection framework designed specifically for Noisy Intermediate-Scale Quantum (NISQ) devices.

Unlike traditional quantum image processing approaches that rely on multi-qubit image encodings (e.g., FRQI, NEQR), PIQED performs edge detection using a single qubit, inspired by human visual perception mechanisms.
The model achieves competitive edge detection quality while minimizing qubit count, circuit depth, and gate complexity.

✨ Key Contributions

✅ Single-Qubit Edge Detection
✅ Constant Circuit Depth (3–4 layers)
✅ Image-Size Independent Complexity
✅ NISQ-Compatible Design
✅ Measurement-Driven Edge Extraction
✅ Strong Performance on Small and Medium Images

🧩 Motivation

Classical edge detection techniques (Sobel, Prewitt, Canny) rely on spatial gradients and convolution operations.
However, existing quantum edge detection models suffer from:

High qubit requirements
Deep controlled circuits
Poor scalability on real quantum hardware
PIQED addresses these limitations by:
Avoiding full quantum image encoding
Encoding pixel intensity differences directly into rotation angles
Extracting edges via quantum measurement statistics

🏗️ PIQED Architecture
🔹 Quantum Circuit Design

Qubits: 1
Gates Used:
Hadamard (H)
Parameterized Rotation (Rz)
Measurement
Circuit Depth: Constant (Independent of image size)

🔹 Processing Pipeline

Input grayscale image
Compute local pixel intensity differences
Map differences to rotation angles
Apply quantum circuit per pixel pair
Measure probability amplitudes
Construct edge intensity map
Post-processing and normalization

📊 Source Databases

This project evaluates performance on medical imaging (Brain Tumor MRI) and remote sensing (SAR Ship Detection) datasets to demonstrate robustness across heterogeneous image domains.

🧠 Brain Tumor Dataset (MRI)

Source Database: Figshare
Dataset Name: Brain Tumor Dataset (Cheng et al.)
Total Images Used: 756 images
Imaging Modality: Contrast-Enhanced MRI
Use Case: Image processing, edge detection, and medical image analysis
Dataset Link:
https://figshare.com/articles/brain_tumor_dataset/1512427

Description:
This dataset contains annotated MRI brain images commonly used in medical image analysis research. It provides clear tumor boundaries and intensity variations, making it suitable for evaluating edge detection and perception-based models.

🛰️ SAR Ship Detection Dataset

Source Database: ICEYE
Dataset Type: Synthetic Aperture Radar (SAR)
Total Images Used: 39,729 SAR images
Image Size for Evaluation: 4 × 4 patches
Use Case: Ship detection, remote sensing, and SAR image processing
Dataset Link:
https://www.iceye.com/downloads/datasets

Description:
The ICEYE SAR Ship Detection dataset consists of high-resolution SAR images captured under varying environmental and sea conditions. SAR imaging enables reliable detection independent of illumination and weather, making it ideal for benchmarking edge detection techniques in remote sensing.

📈 Experimental Configuration

Evaluation Type: Average performance analysis

Patch Size: 4 × 4
Total Images Evaluated:
Brain Tumor MRI: 756 images
SAR Ship Detection: 39,729 images
This dual-domain evaluation validates the generalization capability of the proposed method across medical and remote sensing image modalities.

🧪 Experimental Evaluation
Evaluation Metrics
Mean Squared Error (MSE)
Peak Signal-to-Noise Ratio (PSNR)
Structural Similarity Index (SSIM)

Results Summary
Model	Qubits	Depth	PSNR	SSIM
FRQI-ED	High	Deep	Moderate	Moderate
NEQR-ED	High	Deep	High	High
PIQED	1	Constant	Competitive	High
🚀 Installation
Prerequisites

Python ≥ 3.8
Qiskit
NumPy
OpenCV
Matplotlib

Install Dependencies
pip install qiskit numpy opencv-python matplotlib

▶️ Usage
git clone https://github.com/pirate264/Quantum-Image-Processing.git
cd Quantum-Image-Processing
python piqed_edge_detection.py

Input
Grayscale image (.png, .jpg)

Output
Edge-detected image
Probability maps
Metric evaluation logs

📁 Repository Structure
Quantum-Image-Processing/
│
├── datasets/              # Input images
├── results/               # Output images and metrics
├── circuits/              # Quantum circuit definitions
├── piqed_edge_detection.py
├── evaluation_metrics.py
├── utils.py
├── README.md
└── requirements.txt

🧠 Why PIQED?
Feature	PIQED	Traditional QED
Qubits	1	O(N²)
Depth	Constant	Scales with image
Hardware Ready	✅	❌
Noise Robust	✅	❌
🔮 Future Work

Extension to color images
Multi-directional edge extraction
Hardware execution on IBM Quantum
Hybrid quantum-classical pipelines
Integration with quantum CNNs

📜 Citation
If you use this work, please cite:

@article{PIQED2026,
  title={PIQED: Perception-Inspired Quantum Edge Detection},
  author={Gaurav, Kumar},
  journal={Quantum Image Processing},
  year={2026}
}

🤝 Contributing

Contributions are welcome!
Fork the repository
Create a new branch
Commit your changes
Open a Pull Request

📄 License
This project is licensed under the MIT License.

🔗 GitHub Repository
  https://github.com/pirate264/Quantum-Image-Processing
