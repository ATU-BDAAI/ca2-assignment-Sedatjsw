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

## Pipeline

The pipeline is designed as a multi-modal system:

1. Image preprocessing using OpenCV  
   - grayscale conversion  
   - thresholding techniques  
   - specific adjustments for difficult images (receipt)

2. OCR text extraction using Tesseract  

3. Text preprocessing  
   - cleaning  
   - tokenisation  
   - stopword removal  
   - lemmatisation  

4. TF-IDF feature extraction  

5. Rule-based document classification  

6. Visual feature detection  
   - contour detection  
   - identification of layout regions  

7. Final multi-modal summary combining all outputs  

## Key Observations

From the results, several patterns were observed:

- OCR performance depends heavily on image quality and structure  
- Preprocessing significantly improves OCR results for noisy images  
- Academic documents produce more meaningful keywords due to richer text  
- Financial and receipt documents are more numeric and less descriptive  
- TF-IDF is less effective for short or structured documents  
- Simple rule-based classification works well for small datasets  
- Visual detection highlights layout structure but is limited in precision  

## Technologies Used

- Python  
- OpenCV  
- Tesseract OCR  
- NLTK  
- Scikit-learn  
- Pandas  
- Matplotlib  

## Limitations

This project focuses on demonstrating the pipeline rather than optimising performance.

- The dataset is small and not suitable for training machine learning models  
- OCR errors can affect downstream NLP results  
- The visual detection approach is basic and does not provide precise segmentation  

## Conclusion

This project demonstrates how computer vision and NLP can be combined into a single pipeline to process and analyse documents.

While the system works well for demonstrating the overall process, it also highlights the challenges of working with real-world document data, especially in terms of OCR quality and document variability.
