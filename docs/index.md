# **Fair-Sense-AI**

Fair-Sense-AI is a cutting-edge, AI-driven platform designed to promote transparency, fairness, and equity by analyzing bias in textual and visual content. Whether you're addressing societal biases, identifying disinformation, or fostering responsible AI practices, Fair-Sense-AI equips you with the tools to make informed decisions.

📦 [Fair-Sense-AI on PyPI](https://pypi.org/project/fair-sense-ai/0.1.2/)

---

## **Key Features**

### 📄 **Text Analysis**
- Detect and highlight biases within text, such as targeted language or stereotypes.
- Provide actionable feedback to improve the fairness of content.

### 🖼️ **Image Analysis**
- Extract embedded text from images and evaluate it for potential biases.
- Generate and assess image captions for fairness and inclusivity.

### 📂 **Batch Processing**
- Efficiently analyze large datasets of text or images.
- Automatically flag problematic patterns across datasets.

### 📜 **AI Governance Insights**
- Gain insights into ethical AI practices and bias mitigation strategies.
- Explore topics such as data privacy, transparency, and responsible AI deployment.

---

## **Demo Video**

Watch the demonstration of Fair-Sense-AI below:

<iframe src="https://drive.google.com/file/d/1B0GhvxbJ_dR8xhruOK5cEa_DApTC_xmo/preview" 
        width="500" height="400" allow="autoplay"></iframe>

---

## **Installation**

Install Fair-Sense-AI using pip:

```bash
pip install fair-sense-ai
```

### **Dependencies**
Ensure the following prerequisites are met:
1. Python 3.7+
2. Tesseract OCR for image analysis (installation instructions below).

---

## **Usage Instructions**

### **Launch the Application**

Run the following command to start Fair-Sense-AI:

```bash
fair-sense-ai
```

This will launch a Gradio-powered interface in your default web browser.

---

## **Bias Detection Tutorial**

### **Setup**

1. **Download the Data**:  
   - Our dataset [Newsmediabias-plus](https://huggingface.co/datasets/vector-institute/newsmediabias-plus-clean)
   - Download example datasets from [this Google Drive link](https://drive.google.com/drive/folders/1_D7lTz-TC6yhV7xsZIDzk-tJvl4TAwyi?usp=sharing) to check. Upload the files to your environment (e.g., Jupyter Notebook, Google Colab, etc.).
2. Example Google Colab notebook: [Run the Tutorial](https://colab.research.google.com/drive/1en8JtZTAIa5MuV5OZWYNteYl95Ql9xy7?usp=sharing).


### **Install Required Packages**

```bash
pip install fair-sense-ai
pip uninstall sympy -y
pip install sympy --upgrade
apt update
apt install -y tesseract-ocr
```

---

### **Code Examples**

#### **Text Bias Analysis**

```python
from fairsenseai import analyze_text_for_bias

text_input = "Women are better at multitasking than men."

highlighted_text, detailed_analysis = analyze_text_for_bias(text_input)

print("Highlighted Text:", highlighted_text)
print("Detailed Analysis:", detailed_analysis)
```

#### **Image Bias Analysis**

```python
from fairsenseai import analyze_image_for_bias
from PIL import Image

image = Image.open("example_image.jpg")

highlighted_caption, image_analysis = analyze_image_for_bias(image)

print("Highlighted Caption:", highlighted_caption)
print("Image Analysis:", image_analysis)
```

#### **Launch the Interactive Application**

```python
from fairsenseai import main

main()  # Launches the Gradio interface in a browser
```

---

## **How to Use Fair-Sense-AI**

### **1. Text Analysis**
- Input text into the **Text Analysis** tab of the Gradio interface.
- Click **Analyze** to detect and highlight biases.

### **2. Image Analysis**
- Upload an image in the **Image Analysis** tab.
- Click **Analyze** to evaluate biases in captions or embedded text.

### **3. Batch Text CSV Analysis**
- Upload a CSV file with a `text` column.
- Click **Analyze CSV** to process and flag all entries.

### **4. Batch Image Analysis**
- Upload multiple images in the **Batch Image Analysis** tab.
- Click **Analyze Images** to view results.

### **5. AI Governance Insights**
- Navigate to the **AI Governance and Safety** tab.
- Select a predefined topic or input your own.
- Click **Get Insights** for detailed recommendations.

---

## **Troubleshooting**

### **Common Issues**

- **Slow Model Downloads**:  
  First-time users may experience slow downloads. Ensure a stable internet connection.

- **Tesseract Missing**:  
  Verify Tesseract is installed and accessible in your system's PATH.

- **GPU Acceleration**:  
  Install PyTorch with CUDA support for faster processing.

```bash
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu117
```

---



## **Prerequisites**

1. **Python 3.7+**: Download [here](https://www.python.org/downloads/).
2. **Tesseract OCR**: Required for image text extraction.

   #### Installation Instructions:
   - **Ubuntu**:
     ```bash
     sudo apt-get update
     sudo apt-get install tesseract-ocr
     ```
   - **macOS (Homebrew)**:
     ```bash
     brew install tesseract
     ```
   - **Windows**:
     Download Tesseract OCR from [this link](https://github.com/UB-Mannheim/tesseract/wiki).

---

## **Contact**

For inquiries or support, contact:  
**Shaina Raza, PhD**  
Applied ML Scientist, Responsible AI  
[shaina.raza@vectorinstitute.ai](mailto:shaina.raza@vectorinstitute.ai)

---

## **License**

This project is licensed under the [Creative Commons License](https://creativecommons.org/licenses/).

---
 