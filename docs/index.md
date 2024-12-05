

# **Fair-Sense-AI**

Fair-Sense-AI is a cutting-edge, AI-driven platform designed to promote transparency, fairness, and equity by analyzing bias in textual and visual content. Whether you're addressing societal biases, identifying disinformation, or fostering responsible AI practices, Fair-Sense-AI equips you with the tools to make informed decisions.

---

## **Key Features**

### 📄 **Text Analysis**
- Detect and highlight biases within text, such as targeted language or phrases.
- Provide actionable feedback on the tone and fairness of the content.

### 🖼️ **Image Analysis**
- Extract embedded text from images and analyze it for potential biases.
- Generate captions for images and evaluate their fairness and inclusivity.

### 📂 **Batch Processing**
- Analyze large datasets of text or images efficiently.
- Automatically highlight problematic patterns across entire datasets.

### 📜 **AI Governance Insights**
- Gain detailed insights into ethical AI practices, fairness guidelines, and bias mitigation strategies.
- Explore topics like data privacy, transparency, and responsible AI deployment.

---

## **Installation Guide**

### **Prerequisites**

1. **Python 3.7+**
   - Ensure you have Python installed. Download it [here](https://www.python.org/downloads/).

2. **Tesseract OCR**  
   - Required for extracting text from images.

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
     - Download and install Tesseract OCR from [this link](https://github.com/UB-Mannheim/tesseract/wiki).


### **Installing Fair-Sense-AI**

Install the Fair-Sense-AI package using pip:

```bash
pip install Fair-Sense-AI
```

## **Usage Instructions**

### **Launching the Application**

Run the following command to start Fair-Sense-AI:

```bash
Fair-Sense-AI
```

This will launch the Gradio-powered interface in your default web browser.


## **Bias Detection Tutorial**

### **Setup**

1. **Download the Data**:  
   - Download the data from [this Google Drive link](https://drive.google.com/drive/folders/1_D7lTz-TC6yhV7xsZIDzk-tJvl4TAwyi?usp=sharing).
   - Upload the downloaded files to your environment (e.g., Jupyter Notebook, Google Colab, etc.).

---

### **Install Required Packages**

```bash
!pip install --quiet fair-sense-ai
!pip uninstall sympy -y
!pip install sympy --upgrade
!apt update
!apt install -y tesseract-ocr
```

**Restart your system if you are using Google Colab.**  
Example Colab Notebook: [Run the Tutorial](https://colab.research.google.com/drive/1en8JtZTAIa5MuV5OZWYNteYl95Ql9xy7?usp=sharing)

---

### **Code Examples**

#### **1. Text Bias Analysis**

```python
# Import Required Libraries
from fairsenseai import analyze_text_for_bias

# Example input text to analyze for bias
text_input = "Women are better at multitasking than men."

# Analyze the text for bias using FairSense AI
highlighted_text, detailed_analysis = analyze_text_for_bias(text_input)

# Print the analysis results
print("Highlighted Text:", highlighted_text)
print("Detailed Analysis:", detailed_analysis)
```


#### **2. Image Bias Analysis**

```python
# Import Required Libraries
import requests
from PIL import Image
from io import BytesIO
from fairsenseai import analyze_image_for_bias
from IPython.display import display, HTML

# URL of the image to analyze
image_url = "https://cdn.i-scmp.com/sites/default/files/styles/1200x800/public/images/methode/2018/05/31/20b096c2-64b4-11e8-82ea-2acc56ad2bf7_1280x720_173440.jpg?itok=2I32exTB"

# Fetch and load the image
response = requests.get(image_url)
if response.status_code == 200:
    # Load the image
    image = Image.open(BytesIO(response.content))

    # Resize the image for smaller display
    small_image = image.copy()
    small_image.thumbnail((200, 200))  # Maintain aspect ratio while resizing

    # Display the resized image
    print("Original Image (Resized):")
    display(small_image)

    # Analyze the image for bias
    highlighted_caption, image_analysis = analyze_image_for_bias(image)

    # Print the analysis results
    print("Highlighted Caption:", highlighted_caption)
    print("Image Analysis:", image_analysis)

    # Display highlighted captions (if available)
    if highlighted_caption:
        display(HTML(highlighted_caption))
else:
    print(f"Failed to fetch the image. Status code: {response.status_code}")
```


### **3. Launch the Interactive Application**

```python
from fairsenseai import main

# Launch the Gradio application (will open in the browser)
main()
```

---

## **How to Use Fair-Sense-AI**

### **1. Text Analysis**
- Navigate to the **Text Analysis** tab in the Gradio interface.
- Input or paste the text you want to analyze.
- Click **Analyze** to detect and highlight biases.

### **2. Image Analysis**
- Navigate to the **Image Analysis** tab.
- Upload an image to analyze for biases in embedded text or captions.
- Click **Analyze** to view detailed results.

### **3. Batch Text CSV Analysis**
- Navigate to the **Batch Text CSV Analysis** tab.
- Upload a CSV file with a column named `text`.
- Click **Analyze CSV** to process and analyze all entries.

### **4. Batch Image Analysis**
- Navigate to the **Batch Image Analysis** tab.
- Upload multiple images to analyze biases in captions or embedded text.
- Click **Analyze Images** to view results.

### **5. AI Governance Insights**
- Navigate to the **AI Governance and Safety** tab.
- Choose a predefined topic or input your own.
- Click **Get Insights** for actionable recommendations.

---

## **Troubleshooting**

### **Common Issues**

- **Models Download Slowly**:  
  - On first use, models are downloaded automatically. Ensure you have a stable internet connection.

- **Tesseract Not Found**:  
  - Verify Tesseract is installed and accessible in your system's PATH.

- **GPU Support**:  
  - Install PyTorch with CUDA support if you want GPU acceleration.
  
  ```bash
  pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu117
  ```

---

## **Sample Data**

- A sample CSV file with a `text` column.
- Sample images for analysis.

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
 