# **FairSense API Documentation**

---
## **Introduction**

FairSense is an AI-driven platform for detecting and analyzing bias in textual and visual content. This document outlines the key functions and APIs provided by FairSense for integration and usage.

---

## **1. Core Components**

### **Device Setup**
Sets up the device for model computation (CPU or GPU).
```python
DEVICE = torch.device("cuda" if torch.cuda.is_available() else "cpu")
```

---

### **Model Initialization**
Preloads the required models:
- **Text Model**: `meta-llama/Llama-3.2-1B-Instruct`
- **Image Captioning Model**: `Salesforce/blip-image-captioning-large`
- **Summarizer**: `sshleifer/distilbart-cnn-12-6`

---

## **2. Helper Functions**

### **`post_process_response(response)`**
- **Purpose**: Cleans and summarizes AI model responses.
- **Parameters**:
  - `response` *(str)*: The raw response from the AI model.
- **Returns**: A cleaned and summarized response string.
- **Example**:
  ```python
  processed_response = post_process_response("This is the raw response from the model.")
  print(processed_response)
  ```

---

### **`highlight_bias(text, bias_words)`**
- **Purpose**: Highlights specific biased words in the text.
- **Parameters**:
  - `text` *(str)*: The input text to analyze.
  - `bias_words` *(list)*: A list of words to highlight as biased.
- **Returns**: HTML-formatted text with highlighted bias words.
- **Example**:
  ```python
  highlighted_text = highlight_bias("This is a biased statement.", ["biased"])
  print(highlighted_text)
  ```

---

## **3. Text Analysis**

### **`generate_response_with_model(prompt, progress=None)`**
- **Purpose**: Generates a response from the AI model for a given prompt.
- **Parameters**:
  - `prompt` *(str)*: The input prompt for the model.
  - `progress` *(callable, optional)*: Function to track progress.
- **Returns**: AI-generated response as a string.
- **Example**:
  ```python
  response = generate_response_with_model("Analyze this text for bias.")
  print(response)
  ```

---

### **`analyze_text_for_bias(text_input, progress=gr.Progress())`**
- **Purpose**: Analyzes a given text for bias and provides a detailed analysis.
- **Parameters**:
  - `text_input` *(str)*: Text to analyze.
  - `progress` *(gr.Progress)*: Progress tracker.
- **Returns**: Highlighted text and detailed analysis.
- **Example**:
  ```python
  highlighted, analysis = analyze_text_for_bias("This text may contain bias.")
  print(highlighted)
  print(analysis)
  ```

---

## **4. Image Analysis**

### **`preprocess_image(image)`**
- **Purpose**: Converts images to grayscale and applies thresholding for OCR.
- **Parameters**:
  - `image` *(PIL.Image)*: The input image.
- **Returns**: A preprocessed image for OCR.
- **Example**:
  ```python
  from PIL import Image
  image = Image.open("example.jpg")
  preprocessed = preprocess_image(image)
  preprocessed.show()
  ```

---

### **`analyze_image_for_bias(image, progress=gr.Progress())`**
- **Purpose**: Analyzes an image for bias by extracting text and generating captions.
- **Parameters**:
  - `image` *(PIL.Image)*: The input image.
  - `progress` *(gr.Progress)*: Progress tracker.
- **Returns**: Highlighted captions and detailed analysis.
- **Example**:
  ```python
  image = Image.open("example.jpg")
  highlighted, analysis = analyze_image_for_bias(image)
  print(highlighted)
  print(analysis)
  ```

---

## **5. Batch Processing**

### **`analyze_text_csv(file, output_filename="analysis_results.csv")`**
- **Purpose**: Analyzes a CSV file of text entries for bias.
- **Parameters**:
  - `file` *(File)*: CSV file with text data.
  - `output_filename` *(str)*: Name of the output CSV file.
- **Returns**: An HTML table with analysis results.
- **Example**:
  ```python
  html_table = analyze_text_csv("data.csv")
  print(html_table)
  ```

---

### **`analyze_images_batch(images, output_filename="image_analysis_results.csv")`**
- **Purpose**: Analyzes multiple images for bias.
- **Parameters**:
  - `images` *(list)*: List of image paths.
  - `output_filename` *(str)*: Name of the output file.
- **Returns**: HTML table with analysis results and image previews.
- **Example**:
  ```python
  results = analyze_images_batch(["image1.jpg", "image2.png"])
  print(results)
  ```

---

### **`save_results_to_csv(df, filename="results.csv")`**
- **Purpose**: Saves analysis results to a CSV file.
- **Parameters**:
  - `df` *(pandas.DataFrame)*: DataFrame containing results.
  - `filename` *(str)*: Name of the output file.
- **Returns**: Path to the saved file.
- **Example**:
  ```python
  results_df = pd.DataFrame([{"text": "example", "analysis": "unbiased"}])
  save_path = save_results_to_csv(results_df, "output.csv")
  print(save_path)
  ```

---

## **6. AI Governance**

### **`ai_governance_response(prompt, progress=None)`**
- **Purpose**: Provides insights into AI governance and safety.
- **Parameters**:
  - `prompt` *(str)*: Topic or question about AI governance.
  - `progress` *(callable, optional)*: Progress tracker.
- **Returns**: AI-generated insights and recommendations.
- **Example**:
  ```python
  insights = ai_governance_response("Discuss AI ethics.")
  print(insights)
  ```

---

## **7. AI Safety Dashboard**

### **`display_ai_safety_dashboard()`**
- **Purpose**: Visualizes AI safety risks using interactive charts.
- **Returns**: Tuple containing bar chart, pie chart, scatter plot, and DataFrame.
- **Example**:
  ```python
  fig_bar, fig_pie, fig_scatter, risks_df = display_ai_safety_dashboard()
  fig_bar.show()
  ```

---

# Demo Video

Watch the demonstration of the FairSense platform below:

<iframe src="https://drive.google.com/file/d/1B0GhvxbJ_dR8xhruOK5cEa_DApTC_xmo/preview" 
        width="600" height="450" allow="autoplay"></iframe>



## **Next Steps**

This documentation provides the foundation for integrating FairSense into your workflows. 
**Contact**: For inquiries, collaborations, or feedback, connect with **Shaina Raza, PhD**,  at **shaina.raza@vectorinstitute.ai**.
Let me know if you need anything else added! 😊
 

