# Phishing_Detection
Phishing_Detection with AI


# Phishing URL Detector with LLM API

A complete, end‑to‑end **Phishing URL Detection System** integrating:

* Local LLMs (via **Ollama**)
* Cloud LLMs (via **Hugging Face API**)
* Cyber‑threat intelligence services (VirusTotal, URLScan.io)
* Machine learning models (RandomForestClassifier)
* An interactive dashboard (Streamlit)

This README provides a full technical workflow and the prompts used in Cursor AI to generate each component.

---

## 🔧 Tools & Technologies

* **Cursor AI** – To generate modular code using guided prompts.
* **Ollama** – To run local LLMs.
* **Hugging Face API** – For phishing URL detection using pre‑trained models.
* **VirusTotal API** – For URL scanning and threat analysis.
* **URLScan.io API** – For deep URL and metadata analysis.
* **Python 3.11+**
* **Libraries**: `requests`, `pandas`, `numpy`, `matplotlib`, `transformers`, `ollama`, `virustotal-python`, `urlscanio`

---

## 🧰 Step 1: Set Up the Environment

### **Task**

Create a Python virtual environment and install dependencies.

### **Cursor AI Prompt**

```
Create a Python 3.11+ virtual environment named 'phishing_detector_env'. Install the following packages within the virtual environment: requests, pandas, numpy, matplotlib, transformers, ollama, virustotal-python, urlscanio. Please ensure that the environment is only set up and nothing beyond that.
```

### **Expected Outcome**

Cursor AI outputs commands to:

* Create and activate a virtual environment
* Install required dependencies

---

## 📥 Step 2: Acquire and Preprocess the Dataset

### **Task**

Download, clean, and preprocess the phishing dataset.

### **Cursor AI Prompt**

```
Download the 'PhiUSIIL Phishing URL Dataset' from the UCI Machine Learning Repository. Load the dataset into a pandas DataFrame, handle any missing values by removing rows with NaN values, encode the 'Label' column where 0 = 'BENIGN' and 1 = 'ATTACK', and then split the data into features (X) and target (y). Please only perform these tasks.
```

### **Expected Outcome**

Cursor AI generates code to:

* Download the dataset
* Load it into pandas
* Clean missing values
* Encode labels
* Split into **X** (features) and **y** (target)

---

## 🤖 Step 3: Train the Phishing URL Detection Model

### **Task**

Train a RandomForestClassifier and evaluate it.

### **Cursor AI Prompt**

```
Train a RandomForestClassifier with 100 estimators and a random state of 42 using the dataset. Evaluate the model using a classification report (precision, recall, f1-score). Please only perform the model training and evaluation without any additional processing.
```

### **Expected Outcome**

Cursor AI outputs code that:

* Trains the model
* Prints precision, recall, and F1‑score

---

## 🧠 Step 4: Integrate Hugging Face API for Phishing Detection

### **Task**

Use a pre-trained Hugging Face model to predict phishing probability.

### **Cursor AI Prompt**

```
Integrate the 'pirocheto/phishing-url-detection' model from Hugging Face. Create a function named predict_phishing(url: str) that takes a URL as input and returns the phishing probability. Use only the model for URL classification and nothing beyond that.
```

### **Expected Outcome**

Cursor AI creates:

* API integration
* `predict_phishing(url)` function

---

## 🔍 Step 5: Analyze URLs with VirusTotal API

### **Task**

Integrate VirusTotal API for threat analysis.

### **Cursor AI Prompt**

```
Integrate the VirusTotal API and create a function check_with_virustotal(url: str) that takes a URL and returns the analysis report from VirusTotal. Do not perform any other tasks beyond interacting with the VirusTotal API.
```

### **Expected Outcome**

Cursor AI generates:

* Function to submit URL to VirusTotal
* Extracted analysis report

---

## 🌐 Step 6: Analyze URLs with URLScan.io API

### **Task**

Use URLScan.io to gather URL content/metadata.

### **Cursor AI Prompt**

```
Integrate the URLScan.io API and create a function scan_url(url: str) that takes a URL as input and returns the analysis report from URLScan.io. Do not perform any tasks outside of this specific function.
```

### **Expected Outcome**

Cursor AI generates:

* URL submission function
* Parsed metadata report

---

## 📊 Step 7: Visualize Results in a Dashboard

### **Task**

Create an interactive Streamlit dashboard.

### **Cursor AI Prompt**

```
Create a Streamlit dashboard that includes the following:
A form where a user can input a URL.
The phishing prediction probability from the model (as output from Hugging Face).
The VirusTotal analysis report for the URL.
The URLScan.io analysis report for the URL.
The dashboard should display the results clearly and allow the user to interact with it. Do not perform any other tasks beyond creating the dashboard.
```

### **Expected Outcome**

Cursor AI produces a Streamlit app that:

* Accepts URL input
* Displays ML predictions
* Shows VirusTotal + URLScan.io results
* Provides an interactive dashboard

---

## 📁 Project Structure

```
phishing_detector_env/
│── dashboard.py
│── load_dataset.py
│── predict.py
│── train_model.py
│── test_analysis.py
│── README.md
│── .gitignore
```

---

## 🚀 How to Run the Project

### **1. Activate virtual environment**

```
source phishing_detector_env/bin/activate   # Linux/Mac
phishing_detector_env\Scripts\activate     # Windows
```

### **2. Run the dashboard**

```
streamlit run dashboard.py
```

---

## 📝 Notes

* API keys for VirusTotal and URLScan.io are required.
* Ensure your Hugging Face token is set as an environment variable.
* For local LLM models, install Ollama and download the model.

---





