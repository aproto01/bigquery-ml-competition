<h1 align="center" style="color:#2E5984;">
🚦 BigQuery ML + Generative AI – Traffic Violation Analysis
</h1>

<p align="center">
  <em>A hybrid pipeline combining <strong>computer vision preprocessing</strong>, 
  <strong>BigQuery ML</strong>, and <strong>Generative AI (Gemini Vision)</strong> 
  to transform raw traffic data into <strong>governance-ready insights</strong>.</em>
</p>

---

## 📖 Overview
This repository contains my **Kaggle notebook** and supporting files for a project that blends **CV preprocessing** with **BigQuery ML + Generative AI**.  

The workflow demonstrates how to:  
- 📸 Parse and preprocess **traffic violation evidence** (car plate detection).  
- ☁️ Upload raw & cropped images to **Google Cloud Storage (GCS)**.  
- 🗄️ Store structured evidence in **BigQuery**.  
- 🤖 Use **BigQuery ML** for:  
  - Embedding generation → `ML.GENERATE_EMBEDDING`  
  - Text generation → `ML.GENERATE_TEXT` (Gemini Vision)  
- 📝 Automatically generate:  
  - Officer narratives (fact-based explanations)  
  - Citizen-friendly summaries (plain-language notices)  

---

## 📂 Dataset
- Input: [**Car Plate Detection dataset**](https://www.kaggle.com/datasets/andrewmvd/car-plate-detection) (Pascal VOC XML annotations).  
- Plate crops extracted with **Python + PIL**.  
- Processed images uploaded to GCS, metadata mirrored in **BigQuery dataset** → `traffic_prod_euw4`.  

---

## 🔬 Methodology

1. **Data Preprocessing**  
   - Parsed XML → structured BigQuery tables  
   - Cropped license plates with `PIL`  
   - Synced raw & cropped images to GCS  

2. **BigQuery Integration**  
   - Created dataset/tables (`traffic_prod_euw4`)  
   - Stored evidence: rule, decision, plate text, speed, light state  

3. **Embeddings with BigQuery ML**  
   ```sql
   ML.GENERATE_EMBEDDING

## 🎥 Demo Video
Check out the project demo video:  
[Watch on YouTube →](https://youtu.be/Lnu43vfF5UQ)

---

## ⚙️ Setup Instructions

To reproduce this project and run the notebook on your own environment, you will need:

### 1. Python Dependencies
- Install the required libraries:
  ```python
    pip install -r requirements.txt

### 2. Google Cloud Project
- Create a [Google Cloud Project](https://console.cloud.google.com/).
- Enable the following APIs:
  - **BigQuery API**
  - **BigQuery Connection API**
  - **BigQuery Storage API**
  - **Cloud Storage API**

### 3. BigQuery Dataset & Region
- Create a **BigQuery dataset** in region `europe-west4` (important: Gemini models are only available there).
- Example: `traffic_prod_euw4`.

### 4. Cloud Storage Bucket
- Create a **GCS bucket** (any unique name, e.g., `your-traffic-bucket`).
- Bucket must be in region `europe-west4` for performance and compatibility.

### 5. Service Account & Authentication
- Create a **Service Account** with the following roles:
  - `BigQuery Admin`
  - `Storage Admin`
- Generate a **JSON key** for this service account.
- Store the JSON securely.  
  - On **Kaggle**, use `kaggle_secrets`:
    - `GCP_PROJECT_ID`
    - `GCS_BUCKET`
    - `GCP_SA_KEY` (contents of JSON as a string)

### 6. Update Notebook Variables
In the setup cell, replace placeholders with your own values:

```python
PROJECT_ID = "your-gcp-project-id"
GCS_BUCKET = "your-gcs-bucket"
DATASET    = "traffic_prod_euw4"
LOCATION   = "europe-west4"
CONN_NAME  = "europe-west4.llm-connection"


