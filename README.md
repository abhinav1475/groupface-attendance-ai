# 📸 groupface-attendance-system

An AI-based automated attendance system using **group photo face recognition**. This system leverages **MTCNN** for face detection and **ArcFace** for feature embedding, followed by **cosine similarity** for matching faces against a pre-registered dataset — all done from **static group images**.

---

## 🎯 Project Description

Manual attendance methods are error-prone, time-consuming, and vulnerable to proxies. This project automates attendance using deep learning to identify student faces from a single group photo captured in class.

The system:
- Detects faces using **MTCNN**
- Extracts discriminative embeddings with **ArcFace**
- Matches faces using **cosine similarity**
- Reports **present/absent** students with high accuracy
- Supports **batch image augmentation** to improve generalization

> 📊 Achieved 92% accuracy on custom datasets and 95% on LFW benchmark

---

## 📌 Objectives

- Replace manual roll calls with an efficient, reliable face-based solution.
- Achieve robust recognition in real-world conditions (lighting, occlusion).
- Minimize fraud (e.g., proxy attendance).
- Enable scalable deployment in classrooms using group photos.

---

## 🧠 Methodology

1. **Face Cropping** – Detect and extract faces using **MTCNN**.
2. **Augmentation** – Use `Albumentations` for robust data generation.
3. **Embedding Extraction** – Generate embeddings via **ArcFace** (InsightFace).
4. **Recognition** – Match embeddings using **cosine similarity** and mark attendance.
5. **Validation** – Evaluate performance on real classroom group photos.

---

## 🗂️ Directory Structure

