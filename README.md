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

<img width="1082" height="424" alt="image" src="https://github.com/user-attachments/assets/08d8ad61-476b-4785-90f9-6ec6ce8ca69d" />

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
git clone https://github.com/YOUR_USERNAME/receipt-ocr-pipeline.git

# 2. Install dependencies
pip install -r requirements.txt

# 3. Open the notebook
jupyter notebook Computer_Vision_Project_1.ipynb
```

> Or open directly in [Google Colab](https://colab.research.google.com/drive/1OHTv_KX02xRgSJ9kXHdUqrXJVGVrlrqa?usp=sharing)

---

##  Sample Results

| Receipt | Extracted Date | Extracted Total |
|---------|---------------|-----------------|
| img001  | 12/03/2018    | 45.60           |
| img002  | 05/07/2019    | 120.00          |

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

 
  
    

    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }


  
    
      
      merchant
      date
      total
      total_line
      date_line
      image
    
  
  
    
      0
      HENG KEE DEIISHTS BAK KTJT TEH
      04/01/2018
      42.0
      Total: RM 42.00
      DATE: 04/01/2018 7 : 42:10 AM
      X51005719889.jpg
    
    
      1
      MEDAN NIAGA TASIK DAMAI
      14/02/2018
      45.0
      Total Includes GST 0% 1,45
      14/02/2018 5.37:44PM
      X51005447859.jpg
    
    
      2
      4Z100 KLANG SELANGOR
      None
      NaN
      None
      None
      X51006619863.jpg
    
    
      3
      SECURITY & OATRADING
      None
      NaN
      None
      None
      X51006619784.jpg
    
    
      4
      42100 KLANG SELANGOR
      None
      NaN
      None
      None
      X51006733495.jpg
    
  


    

  
    

  
    
  
    

  
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  

    
      const buttonEl =
        document.querySelector('#df-0435217b-d996-4cfd-be1a-48a7c123b77e button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-0435217b-d996-4cfd-be1a-48a7c123b77e');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    
  


    
  

