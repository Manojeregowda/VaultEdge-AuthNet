# 🏦 VaultEdge-AuthNet  

**VaultEdge-AuthNet** is a **Flask-based Machine Learning API** for **Banknote Authentication**.  
It predicts whether a **banknote is genuine or forged** using **numerical features** (`variance`, `skewness`, `curtosis`, `entropy`) derived from image analysis — *not raw images*.  

The model is powered by a **RandomForestClassifier**, integrated into a **Flask REST API**, documented using **Flasgger (Swagger UI)**, and fully containerized using **Docker** for easy deployment.  

---

## ✨ Key Features  

✅ **RandomForestClassifier Model** – Predicts genuine vs forged notes with high accuracy.  
✅ **Flask REST API** – Lightweight backend for real-time ML inference.  
✅ **Swagger UI via Flasgger** – Interactive, auto-generated API documentation.  
✅ **Dockerized Deployment** – Build once, run anywhere.  
✅ **CSV File Uploads** – Supports batch predictions.  
✅ **No Image Input Needed** – Uses numerical features only.  

---

## 🧠 How It Works  

The dataset **(`BankNote_Authentication.csv`)** contains the following features:  

- **Variance** of Wavelet Transformed Image  
- **Skewness**  
- **Curtosis**  
- **Entropy**  
- **Output Class** → `0 = Forged`, `1 = Genuine`  

### 🔹 Steps:
1. A **RandomForestClassifier** is trained on this dataset.  
2. The trained model (**`classifier.pkl`**) is loaded into a Flask API.  
3. Users can:  
   - Pass numerical inputs directly via **GET requests**, or  
   - Upload a **CSV file** for batch predictions.  
4. The API is automatically documented using **Flasgger**, accessible via Swagger UI.  

---

## ⚙️ Setup Instructions  

### 🔹 Clone the Repository  
git clone https://github.com/YOUR_USERNAME/VaultEdge-AuthNet.git
cd VaultEdge-AuthNet

Create a Virtual Environment
python -m venv venv
venv\Scripts\activate      # For Windows
or
source venv/bin/activate   # For macOS/Linux
pip install -r requirements.txt

python flask_api_copy.py
Swagger UI → http://127.0.0.1:5000/apidocs

# or

Run with Docker
Build Docker Image
docker build -t vaultedge-authnet .

Run Docker Container
docker run -p 5000:5000 vaultedge-authnet

Now open 👉 http://127.0.0.1:5000/apidocs
