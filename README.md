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
