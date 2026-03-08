#  Receipt OCR Pipeline (SROIE)

> End-to-end OCR pipeline to extract **Merchant**, **Date**, and **Total**
> from scanned receipts using OpenCV and EasyOCR.

![Python](https://img.shields.io/badge/Python-3.10-blue)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green)
![EasyOCR](https://img.shields.io/badge/EasyOCR-1.x-orange)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

##  Project Overview

This is my first Computer Vision project. It builds a complete OCR pipeline
that reads receipt images from the SROIE dataset, preprocesses them with
OpenCV (grayscale conversion, CLAHE contrast enhancement, adaptive
thresholding), and then uses EasyOCR to extract text and regex rules to
parse out structured fields.

**Output:** A CSV file with one row per receipt containing extracted fields.
<img width="455" height="658" alt="image" src="https://github.com/user-attachments/assets/3c6a9d2c-955c-49a1-8d22-36e431d8e273" />


<img width="564" height="790" alt="image" src="https://github.com/user-attachments/assets/8b911ee2-f3f2-4c22-8c75-4968ca0af7a0" />



---

##  Dataset

- **Name:** SROIE Dataset v2
- **Source:** [Kaggle – urbikn/sroie-datasetv2](https://www.kaggle.com/datasets/urbikn/sroie-datasetv2)
- **Contents:** Scanned receipt images with ground-truth annotations

---

##  Tech Stack

| Tool       | Purpose                              |
|------------|--------------------------------------|
| Python     | Core language                        |
| OpenCV     | Image preprocessing                  |
| EasyOCR    | Optical character recognition        |
| Regex      | Rule-based field extraction          |
| Pandas     | Output CSV generation                |
| Google Colab | Cloud execution environment        |

---

##  Pipeline Steps

1. **Load Images** — Batch load receipt `.jpg` files
2. **Grayscale Conversion** — Remove colour to simplify data
3. **CLAHE Enhancement** — Improve contrast on faded receipts
4. **Adaptive Thresholding** — Binarise for cleaner OCR input
5. **EasyOCR** — Extract raw text with bounding boxes
6. **Sorting** — Reorder detections into natural reading order
7. **Field Extraction** — Regex to pull Date and Total values
8. **CSV Export** — Save structured output to `receipt_predictions.csv`

---

##  How to Run

```bash
# 1. Clone the repo
git clone https://github.com/Code-blize/receipt-ocr-pipeline.git

# 2. Install dependencies
pip install -r requirements.txt

# 3. Open the notebook
jupyter notebook Computer_Vision_Project_1.ipynb
```

> Or open directly in [Google Colab](https://colab.research.google.com/drive/1OHTv_KX02xRgSJ9kXHdUqrXJVGVrlrqa?usp=sharing)

---

##  Sample Results

| Receipt Image     | Merchant                      | Date       | Total |
|------------------|-------------------------------|------------|-------|
| X51005719889.jpg | HENG KEE DEIISHTS BAK KTJT TEH | 04/01/2018 | 42.0  |
| X51005447859.jpg | MEDAN NIAGA TASIK DAMAI       | 14/02/2018 | 45.0  |
| X51006619863.jpg | 4Z100 KLANG SELANGOR          | None       | NaN   |
| X51006619784.jpg | SECURITY & OTRADING           | None       | NaN   |
| X51006733495.jpg | 42100 KLANG SELANGOR          | None       | NaN   |

<img width="1082" height="424" alt="image" src="https://github.com/user-attachments/assets/08d8ad61-476b-4785-90f9-6ec6ce8ca69d" /> 
---

##  What I Learned

- How to preprocess images for OCR using OpenCV
- The difference between Tesseract and EasyOCR
- How adaptive thresholding improves text detection on noisy scans
- Regex-based information extraction from unstructured text

---

##  Future Improvements

- [ ] Train a custom model for Malaysian receipt formats
- [ ] Build a Gradio or Streamlit demo app
- [ ] Evaluate F1 score against SROIE ground truth labels

---

##  Author

**Obasi-Uzoma Blessing**
- GitHub: [@Code-blize](https://github.com/Code-blize)
- LinkedIn: [blessingobasiuzoma](https://linkedin.com/in/blessingobasiuzoma)

---

##  License

This project is licensed under the MIT License.
  


    
  

