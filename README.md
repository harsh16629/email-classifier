# email-classifier

# Email Classification Using a Transformer-Based Model

## 1. Overview

This project focuses on classifying emails into distinct categories: **Product A Inquiry, Product B Inquiry, Product C Inquiry, and a combined Product A / Product B Inquiry**. To achieve this, we utilize a **Transformer-based model (BERT)** and fine-tune it using labeled email data.

### Key Steps:

1.  **Preprocessing** – Tokenizing and encoding email text.
    
2.  **Model Training** – Fine-tuning a pre-trained BERT model for classification.
    
3.  **Evaluation** – Measuring key performance metrics such as accuracy, precision, recall, and F1-score.
    
4.  **Deployment** – Implementing a script to classify new email inputs.
    

----------

## 2. Data Preparation & Preprocessing

### **Dataset & Labeling**

-   The dataset consists of email samples labeled into four categories:
    
    -   **Product A Inquiry (0)**
        
    -   **Product B Inquiry (1)**
        
    -   **Product C Inquiry (2)**
        
    -   **Product A / Product B Inquiry (3)**
   
        
-   An **80-20 split** is applied to separate training and validation sets, ensuring even representation across all categories.
    

### **Text Tokenization**

-   BERT's tokenizer processes email text by converting it into numerical sequences.
    
-   Tokenized inputs are **padded or truncated** to a maximum length of 128 tokens for uniformity.
    

----------

## 3. Model Training & Optimization

### **Model Selection**

-   **BERT-base-uncased** is chosen as the foundation due to its strong contextual understanding.
    
-   A classification head is added to map inputs to the four predefined categories.
    

### **Loss Function & Optimizer**

-   **Cross-Entropy Loss** is used, as it is well-suited for multi-class classification.
    
-   To mitigate potential class imbalance, stratified sampling is applied.
    
-   **AdamW optimizer** with weight decay (`0.01`) is implemented for stability.
    

### **Training Configuration**

-   **Batch Size:** 2
    
-   **Epochs:** 5
    
-   **Learning Rate:** 1e-5
    
-   **Evaluation Strategy:** Performance metrics computed at the end of each epoch.
    

----------

## 4. Model Evaluation & Results

Performance is assessed using key metrics:

| Metric  | Value |
|---------------|-------|
| Precision  | 100%  |
| Validation Loss | 2.31  |

-   **Precision** indicate how well each category is identified.
    
-   **Validation loss** is monitored to detect overfitting.
    

### **Observations & Improvements**

-   The model successfully classifies straightforward cases.
    
-   Some misclassifications occur in ambiguous email inquiries involving multiple products.
    
-   Enhancements such as increasing the original dataset and fine-tuning hyperparameters can improve performance.
    

----------

## 5. Deployment & Future Enhancements

-   A Python script enables real-time classification of new emails.
    
-   The fine-tuned model is stored for quick inference.
    
-   Potential improvements include API integration for seamless email sorting in business applications.
    

----------

## 6. Conclusion

This project demonstrates the practical use of Transformer-based models for email classification. Through fine-tuning and strategic preprocessing, the system can effectively distinguish between different product inquiries. Further enhancements, such as additional training data and model refinement, will further boost its accuracy and reliability in real-world applications. 
