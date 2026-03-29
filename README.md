# Robust Real-Time Perception for Autonomous Systems (TSDR)

[![Framework: YOLOv8](https://img.shields.io/badge/Framework-YOLOv8-green.svg)](https://github.com/ultralytics/ultralytics)
[![Field: Robotics](https://img.shields.io/badge/Field-Robotics-blue.svg)](#)
[![Status: Operational](https://img.shields.io/badge/Status-Operational-brightgreen.svg)](#)

## 📌 Research Overview
This project implements a high-performance **Traffic Sign Detection and Recognition (TSDR)** system, a critical component for autonomous navigation and robotic environmental awareness. Utilizing the **YOLOv8 (You Only Look Once)** architecture, this pipeline is designed to identify, localize, and classify road signs in real-time.

The core focus is on **Efficient AI**: maximizing detection accuracy (mAP) while maintaining the low latency required for high-velocity autonomous agents (e.g., rovers, self-driving platforms).

---

## 🚀 Key Technical Implementation
* **Model Backbone:** Fine-tuned the **YOLOv8-Nano (yolov8n)** variant—a 3.2M parameter model optimized for deployment on edge-computing hardware (NVIDIA Jetson, Raspberry Pi).
* **Spatial Mapping:** Integrated bounding-box regression to extract precise 2D coordinates for obstacle avoidance and path-planning modules.
* **Optimized Inference:** Configured the pipeline for GPU-accelerated processing, achieving inference speeds of **~2.5ms per frame**.
* **Deployment Ready:** Exported the final weights to **ONNX format** to ensure cross-platform compatibility and hardware-agnostic execution.

# Real-Time Traffic Sign Detection and Recognition (TSDR)

[![Model: YOLOv8](https://img.shields.io/badge/Model-YOLOv8-B121FF.svg)](https://github.com/ultralytics/ultralytics)
[![Runtime: PyTorch](https://img.shields.io/badge/Runtime-PyTorch-EE4C2C.svg)](https://pytorch.org/)
[![Export: ONNX](https://img.shields.io/badge/Export-ONNX-005AD4.svg)](https://onnx.ai/)

## 🛠 Technical Specifications

### 1. Model Architecture
* **Backbone:** YOLOv8n (Nano) – Optimized for minimal parameter count (3.2M) and high-speed throughput.
* **Task:** Object Detection (Localization + Classification).
* **Framework:** Ultralytics YOLOv8.
* **Inference Engine:** Single-pass regression-based detection utilizing a Cross-Stage Partial (CSP) Darknet backbone.

### 2. Computing Environment
* **Hardware:** Optimized for NVIDIA Tesla T4 GPU (CUDA 11.8/12.1).
* **Environment:** Python 3.10.12.
* **Core Dependencies:**
    * `ultralytics` (latest)
    * `torch` >= 2.0.0
    * `onnx` == 1.14.1
    * `onnxslim` == 0.1.90
    * `opencv-python` (cv2)

### 3. Training & Inference Pipeline
* **Input Resolution:** 640x640 pixels.
* **Preprocessing:** Image normalization, tensor resizing, and automatic feature extraction via convolutional layers.
* **Post-processing:** Non-Maximum Suppression (NMS) to eliminate redundant bounding boxes based on Intersection over Union (IoU) thresholds.
* **Metric Support:** Evaluation focused on Mean Average Precision (mAP) and per-class confidence scoring.

### 4. Optimization & Model Export
* **Format:** Exported to **ONNX** (Open Neural Network Exchange) format using **opset 17**.
* **Slimming:** Post-export optimization performed using `onnxslim` to reduce model size and remove redundant nodes for edge deployment.
* **Dynamic Support:** Capable of handling both batch and single-stream inference.

### 5. Dataset Structure
* **Class Count:** Multi-class detection covering 40+ unique traffic sign categories.
* **Labels:** Bounding boxes stored in YOLO text format (normalized `x_center`, `y_center`, `width`, `height`).
* **Categories:** Includes Regulatory, Warning, and Informational signage.

## 📂 Repository Contents
* `Real_Time_TSDR_Optimization.ipynb`: Full implementation, including library updates, training logs, and inference testing.
* `best.onnx`: The optimized, ready-to-deploy model weight file.
* `data.yaml`: Configuration file defining paths and class mappings for the YOLOv8 engine.
* `results.png`: Visual validation of model inference.

## 📊 Performance Benchmarks
| Metric | Value |
| :--- | :--- |
| **Inference Speed** | ~2.5ms per frame (GPU) |
| **Model Size** | Optimized via ONNX-Slim |
| **Classes** | 50+ Traffic Sign Categories |
