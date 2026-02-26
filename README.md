Road Damage Detection Using SAM Segmentation & YOLOv11m
This repository contains an automated pipeline for detecting and segmenting road hazards like cracks and potholes, specifically optimized for Indian road conditions. By combining YOLOv11m for real-time object detection and SAM (Segment Anything Model) for pixel-level segmentation, this project aims to replace manual, error-prone road inspections.
+4

## Project Overview

Goal: To train and evaluate models for automatic detection and segmentation of Indian road damages under diverse conditions.


Motivation: To create a real-time system that assesses road safety and driving comfort.
+1


Technology: Uses YOLO for fast detection and SAM for precise localization of damaged regions.

## Dataset Description
The project utilizes the RDD2022 (India subset):


Image Count: 9,200 images of Indian roads.

Damage Classes:


D00: Longitudinal cracks 


D10: Transverse cracks 


D20: Alligator cracks 


D40: Potholes 


Annotation: YOLO-format bounding boxes.

## Methodology & Workflow

Data Collection: Images sourced from the RDD2020 (India subset).


Preprocessing: Images resized to 640×640, normalized, and cleaned.


Augmentation: Applied mosaic, blur, flips, and rotations to improve generalization.


Model Training: Fine-tuned YOLOv11m (pretrained on COCO) for 50 epochs.


Segmentation Integration: Integrated SAM in zero-shot mode to generate pixel-level masks on detected regions.

## Experimental Results
The model was evaluated using a 70/20/10 split.

Metric	Value
Precision (B)	
0.589 

Recall (B)	
0.279 

mAP@50 (B)	
0.284 

mAP@50-95 (B)	
0.145 


Export to Sheets

### Key Findings

Strong Detection: High accuracy for D20 (Alligator cracks) and D40 (Potholes).
+1


Challenges: Slight difficulty with D00 (Longitudinal cracks) due to their narrow width and low contrast.
+1


Zero-Shot Success: SAM demonstrated accurate pixel-level segmentation without requiring retraining.

## Project Structure

DeepLearningPPT.pptx: Project presentation.


Model Workflow: Visual representation of the detection-to-segmentation pipeline.

## Contributors

Chinmaya Sahu: Data Preparation & Preprocessing 


Arup Pattnaik: Integration & Optimization 


Sarbajeet Muduli: Model Development & Training 


Sanjeev Swain: Documentation & Results Visualization 


Ayman Ahmed: Experimental Setup & Evaluation 

Supervised by: DR. Chinmayee Dora, Centurion University 

### References
Maeda et al. (2020) - RDD2020 Dataset Source.

Kirillov et al. (2023) - Segment Anything.

Jocher & Ultralytics Team (2025) - YOLOv11.
