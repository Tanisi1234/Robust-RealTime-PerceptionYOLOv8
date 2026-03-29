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

---

## 🛠 Tech Stack & Tools
* **Deep Learning:** PyTorch, Ultralytics YOLOv8
* **Computer Vision:** OpenCV (Real-time stream processing)
* **Performance Analysis:** Matplotlib, NumPy
* **Environment:** Python 3.10+, CUDA-accelerated kernels

---

## 📊 Performance Benchmark
| Metric | Value |
| :--- | :--- |
| **Model** | YOLOv8-Nano |
| **Inference Latency** | < 3ms (GPU) |
| **Input Resolution** | 640 x 640 |
| **Export Formats** | PyTorch (.pt), ONNX, TensorRT |

---

## 🎓 Relevance to RAD Lab (Robotic Systems)
This perception pipeline directly addresses the challenges of **Autonomous Navigation in Unstructured Environments**. By focusing on real-time object detection and classification, the methodology is applicable to:
1. **Planetary Exploration:** Visual marker recognition for rover localization.
2. **Hazard Detection:** Real-time identification of navigation-critical signage or environmental obstacles.
3. **Edge-Computing:** Proving that sophisticated CV models can run on low-power robotic controllers.

---

## 👨‍💻 Author
**Tanisi Jha**
*B.Tech in Electronics and Communication Engineering*
*Recipient of the ISRO Research Excellence Award (2025)*

---
*Note: This repository is part of a research portfolio exploring the intersection of Signal Processing, Computer Vision, and Autonomous Robotics.*
