# YOLOv10 for Pomegranate Yield Estimation and Loss Detection

Implementation of the YOLOv10 deep learning algorithm for detecting pomegranates in low-quality orchard images, improving model accuracy through architecture modification and model optimization to address challenges in detecting small, dark, and defective fruits.

Run this project via [Colab Link](https://colab.research.google.com/drive/1DgS6s2LFoq2O4ulE1rSIyUxwzFmrDgIg?usp=sharing#scrollTo=3GGYGMuyCbCl)

## Dataset:
- 117 high-resolution images from 30 pomegranate trees.  
- Captured from both sunlit and shaded sides in various angles.  
- Split into Training (70%), Testing (15%), and Validation (15%). 
<div align="center">
  <img src="https://github.com/user-attachments/assets/32e4e923-49f9-4261-8e7a-da557063f211" width="400"/>
</div>
- Images are categorized into two classes: Healthy fruits and Defective/Cracked fruits.
<div align="center">
  <img src="https://github.com/user-attachments/assets/e1e170cc-28e3-481d-804d-20024b32844c" width="400" height="300"/>
</div>


## Main Challenges:  
- Noise from leaves, dust, and lighting variations hinder detection in the field.  
- Complexity of real-world environments with occlusions from foliage, branches, and fruit clusters.  
- Small, hard-to-detect objects.  
- Imbalanced dataset.

## YOLOv10 Algorithm: 
YOLO (You Only Look Once) is a well-known real-time object detection algorithm. The architecture includes three main components:  
- Backbone: Extracts features using convolutional layers and advanced layers like C2f and SCDown for enhanced feature learning.  
- Neck: Combines multi-level information to improve detection quality.  
- Head: The final layer, where object detection occurs, including bounding box and label predictions.  
YOLOv10 is available in multiple model variants (n, s, m, l, xl) to balance speed and accuracy depending on hardware and task requirements.

## Baisline Results:
The default YOLOv10 model was evaluated using a learning rate of 0.001. 
The model showed high precision for both "pomegranate" and "defective" categories, but recall and F1-score were notably low for the "defective" category.  
<div align="center">
  <img src="https://github.com/user-attachments/assets/0509bdbe-3989-42f4-932d-d582ce383fc6" width="400"/>
</div>

## Alterations and Improvements:
- **Hyperparameter tuning**: Slight improvement in accuracy (0.38).  
- **Model variant transition**: Moved from the Nano to the Small variant, improving all metrics (accuracy: 0.44).  
- **Residual connections**: Enabled in the C2fCIB block, leading to a minor improvement in accuracy (0.451).  
- **Activation functions**: Experimented with ReLU6 and Mish, resulting in similar results (decline in performance).  
- **Kernel size adjustment**: Defined kernel size in the RepVGG block, resulting in a minor accuracy boost (0.455).  
- **Final hyperparameter tuning**: Major improvement in accuracy (0.5353). 

## Performance Comparison:
The optimized model showed a significant improvement in recall, especially for defective pomegranates (+121%), enhancing both defect detection and yield estimation.
<div align="center">
  <img src="https://github.com/user-attachments/assets/78cceff8-a35f-4b77-887b-c725bd4ac85b" width="400"/>
</div>

## Conclusion
This project demonstrates the potential of YOLOv10 for pomegranate yield estimation and loss detection. Future work may involve refining the model further and applying it to larger datasets for real-time agricultural monitoring.

## What I Learned:
- Applied YOLOv10 for object detection and model optimization.
- Improved hyperparameter tuning and model performance.
- Handled imbalanced datasets and real-world data challenges.
- Gained experience in deep learning for practical, data-driven solutions.
