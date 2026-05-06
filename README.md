# Multi-modal Document Understanding (CA2)

This project presents a document processing pipeline that combines Computer Vision and Natural Language Processing (NLP) techniques to analyse different types of real-world documents.

## Project Overview

The aim of this project is to explore how different techniques can be combined into a single pipeline to process and understand document images.

The system works on a small set of documents with different structures:

- Academic poster  
- Booking confirmation form  
- Financial documents (invoice and statement)  
- Pharmacy receipt  

Each document is processed using the same pipeline, allowing comparison of how different document types behave under identical processing steps.

---

## Pipeline

The pipeline is designed as a multi-modal system:

### Image preprocessing (OpenCV)
- grayscale conversion  
- thresholding techniques  
- noise reduction  
- specific adjustments for difficult images (e.g. receipt)  

### OCR text extraction (Tesseract)

### Text preprocessing
- cleaning  
- tokenisation  
- stopword removal  
- lemmatisation  

### Text feature extraction
- TF-IDF  
- key phrase extraction  

### Named Entity Recognition
- rule-based extraction (dates, monetary values, phone numbers, names)  
- spaCy-based NER (organisations, people, locations, dates, monetary values)  

### Document classification
- rule-based classification based on extracted features  

### Visual feature detection
- contour detection  
- identification of layout regions  
- structured region detection (tables, forms, invoice and receipt sections)  

### Image segmentation
- segmentation of documents into meaningful regions  
- grouping text blocks, tables and visual components  

### Multi-modal integration
- combining OCR text, NLP features, named entities, visual regions and segmentation results  

### Final output
- structured table summarising text, entities, visual features and document insights  

---

## Key Observations

From the results, several patterns were observed:

- OCR performance depends heavily on image quality and structure  
- Preprocessing significantly improves OCR results for noisy images  
- Academic documents produce more meaningful keywords due to richer text  
- Financial and receipt documents are more numeric and less descriptive  
- TF-IDF is less effective for short or structured documents  
- Simple rule-based classification works well for small datasets  
- Visual detection highlights layout structure but is limited in precision, especially for complex documents  
- Dense documents such as academic posters produce many detected regions due to complex layouts  

---

## Technologies Used

- Python  
- OpenCV  
- Tesseract OCR  
- NLTK  
- spaCy  
- Scikit-learn  
- Pandas  
- Matplotlib  

---

## Limitations

This project focuses on demonstrating a complete pipeline rather than optimising performance.

- The dataset is small and not suitable for training machine learning models  
- OCR errors can affect downstream NLP results  
- The visual detection approach is contour-based and not highly precise  
- Complex document layouts (e.g. posters) produce many detected regions  
- Named Entity Recognition may be affected by OCR noise  

---

## Conclusion

This project demonstrates how computer vision and NLP can be combined into a single pipeline to process and analyse documents.

The inclusion of enhanced named entity recognition (spaCy) and structured region detection improves both text understanding and visual analysis.

While the system works well for demonstrating the overall process, it also highlights the challenges of working with real-world document data, especially in terms of OCR quality, layout complexity and document variability.
