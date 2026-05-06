# Multi-modal Document Understanding (CA2)

This project presents a document processing pipeline that combines Computer Vision and Natural Language Processing (NLP) techniques to analyse different types of real-world document images.

## Project Overview

The aim of this project is to understand how different techniques can be combined into a single pipeline to process and analyse document images.

The focus of this work is on building a complete pipeline and understanding how each stage contributes to the final output, rather than developing a highly optimised system.

The system works on a small set of documents with different structures:

- Academic poster  
- Booking confirmation form  
- Financial documents (invoice and statement)  
- Pharmacy receipt  

Each document is processed using the same pipeline, which makes it easier to compare how different document types behave under the same processing steps.

---

## Pipeline

The pipeline is designed as a multi-modal system:

### Image preprocessing (OpenCV)
- grayscale conversion  
- thresholding techniques  
- noise reduction  
- specific adjustments for difficult images (e.g. receipt)  

### OCR text extraction (Tesseract)
- extraction of raw text from document images  

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
- structured table summarising text, entities, visual features and document-level insights  

---

## Key Observations

- OCR performance depends heavily on image quality and document structure  
- Image preprocessing significantly improves OCR results for noisy images  
- Academic documents produce more meaningful keywords due to richer text  
- Financial and receipt documents are more numeric and structured  
- TF-IDF is less effective for short or highly structured documents  
- Rule-based classification works well for small datasets  
- Visual detection highlights layout structure but is limited in precision  
- Complex documents (such as posters) produce many detected regions due to dense layouts  

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

This project focuses on demonstrating the pipeline rather than optimising performance.

- The dataset is small and not suitable for training machine learning models  
- OCR errors can affect downstream NLP results  
- The visual detection approach is contour-based and not highly precise  
- Complex layouts (e.g. posters) produce many detected regions  
- Named Entity Recognition can be affected by OCR noise  

---

## Conclusion

This project demonstrates how Computer Vision and NLP can be combined into a single pipeline for document understanding.

The addition of enhanced named entity recognition (spaCy) and structured region detection improves both text analysis and visual understanding.

Overall, the system works well as a complete pipeline, while also highlighting real-world challenges such as OCR quality, layout complexity and document variability.

---

## Author

Sedat Aydin  
Postgraduate Diploma in Big Data Analytics & AI  
Atlantic Technological University
