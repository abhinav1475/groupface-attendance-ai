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
groupface-attendance-system/
├── face_dataset_generation.py # Face detection & cropping using MTCNN
├── augmentation_.py # Augment face dataset (Albumentations)
├── Arc_face_Training.py # Extract embeddings & save labels
├── recognise_faces.py # Run face recognition & generate reports
├── main.py # Unified entry point for the entire system
├── README.md # You're here!


---

## ⚙️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/groupface-attendance-system.git
cd groupface-attendance-system
pip install -r requirements.txt

🚀 How to Run the Project
Step 1: Generate Face Crops
python face_dataset_generation.py
Detects and crops faces from raw .jpg files in /imgs and saves them to /faces.

Step 2: Augment Faces
python augmentation_.py
Creates 10 augmented images per face using rotation, flip, scale, etc., and saves to /augmented_faces.

Step 3: Extract Embeddings
python Arc_face_Training.py
Uses InsightFace to extract facial embeddings and saves them as .pkl files.

Step 4: Recognize Faces in Group Photo
python recognise_faces.py
Input: Group photo (e.g., group_test_1.jpg)
Output: Image with bounding boxes + attendance report (present/absent)


---

## 📈 Results Summary

| Metric       | Score   |
|--------------|---------|
| **Accuracy** | 92%     |
| **Precision**| 91%     |
| **Recall**   | 93%     |
| **F1 Score** | 0.92    |
| **AUC (LFW)**| 0.9911  |
| **EER**      | 0.042   |

- The model showed strong performance in group image settings and maintained high generalization on the LFW benchmark dataset.
- Face detection and embedding recognition handled occlusion and lighting variation well due to MTCNN and ArcFace robustness.

---

## 🧪 Dataset Notes

- **Number of students**: 23
- **Images per student**: ~150 (including augmentations)
- **Image collection**: Captured using an iPhone 14 Pro Max in real classroom settings.
- **Augmentation**: Horizontal flips, brightness shifts, rotations, blurs, and scale transforms.
- **Group photos**: Used for validation — tested in multiple lighting and occlusion conditions.

---

## 📚 Citation & Credits

This project is based on the research paper:

> *Automated Attendance Monitoring Using Group Photo-Based Face Recognition: A Deep Learning Approach for Educational Institutions*  
> **Authors**:  
> Abhinav Garlapati, Pavan Kumar Challapalli, Shiva Shankar Reddy Tara  
> Siddhartha Academy of Higher Education, Vijayawada, India

For academic or research use, please cite this work accordingly.

---

## 🔮 Future Enhancements

- **Liveliness Detection**: Add spoof prevention using liveliness verification.
- **Mobile & Edge Deployment**: Optimize for real-time performance on Raspberry Pi or mobile apps.
- **CMS Integration**: Expand backend attendance logging and reporting.
- **Cybersecurity**: Encrypt face embeddings and attendance data for secure transmission and storage.
- **Multiclass Scalability**: Train and test across departments and year-wise sections dynamically.
- **Face ID Updates**: Enable retraining when students update their reference images.

---

## 🛡️ License

MIT License – open for academic and educational use.




