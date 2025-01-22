# Emotion Detection

In this project, We worked on cleaning the [FER2013 dataset](https://www.kaggle.com/datasets/msambare/fer2013) from Kaggle and training some deep learing models to detect facial emotions. The dataset still requires additional preprocessing to improve metric values and overall model predictions. Below are the steps we followed during preprocessing:

### Preprocessing Steps
1. **Noise Removal**: Identified and removed images composed of a single pixel value.
2. **Duplicate Removal**: Used a hash function to detect duplicates, followed by:
   - Manually correcting or removing misclassified images by displaying cross-class duplicates and visually determining the correct class. Duplicates in other classes were subsequently removed.
   - Calling the Gemini API for automated missclassification detection.

### Models and Evaluation
We trained and evaluated the following models:
1. **Custom CNN Model**: Built with neural network layers.
2. **VGG16**: A pre-trained VGG model fine-tuned for emotion detection.
3. **ResNet50**: Another pre-trained model fine-tuned for this task.

Below are the results for each model, including visualizations of performance and evaluation metrics.

---

## Custom CNN Model
<div align="center">
  <img src="https://github.com/user-attachments/assets/1885b5cd-124b-414b-9d9b-01117f459649" alt="cnn arch" width="30%">
</div>


### Metrics Evolution
![cnn met](https://github.com/user-attachments/assets/b27234ed-f2f6-4888-9925-d05cc4873e84)

### Correlation Matrices
- **Validation Set**:
<div align="center">
  <img src="https://github.com/user-attachments/assets/a35bd541-3a9b-421a-8443-9617355c45d2" alt="corr1" width="50%">
</div>

- **Test Set**:
<div align="center">
  <img src="https://github.com/user-attachments/assets/6e471b69-a375-4173-9353-d341aa77bbe5" alt="corr2" width="50%">
</div>

### ROC Curve
<div align="center">
  <img src="https://github.com/user-attachments/assets/2d1f9ac9-a5a9-494c-886a-cbc0a3004b38" alt="ROC" width="50%">
</div>


### Test Evaluation
- **Loss**: `1.2643`
- **Accuracy**: `88.48%`
- **Precision**: `71.58%`
- **Recall**: `32.15%`
- **F1-Score**: `41.77%`
- **AUC**: `86.20%`

---

## VGG16 Model
### Model Architecture
<div align="center">
  <img src="https://github.com/user-attachments/assets/827c1701-5df9-46a2-b8ab-13fd180c9bfa" alt="VGG" width="30%">
</div>

### Metrics Evolution
![vgg metrics](https://github.com/user-attachments/assets/3b0f0395-161a-4623-b659-2f27fedfb2f7)


### Test Evaluation
- **Loss**: `1.6514`
- **Accuracy**: `86.17%`
- **Precision**: `76.83%`
- **Recall**: `4.61%`
- **F1-Score**: `8.57%`
- **AUC**: `74.17%`

---

## ResNet50 Model
### Model Architecture

<div align="center">
  <img src="https://github.com/user-attachments/assets/2daa977d-c5df-4fde-a7d5-d4d1fba96e65" alt="cnn arch" width="50%">
</div>

### Metrics Evolution
![resnet metric](https://github.com/user-attachments/assets/456aa58d-702e-41da-ae07-f0ce70bfa5fe)


### Test Evaluation
- **Loss**: `1.9471`
- **Accuracy**: `85.71%`
- **Precision**: `0%`
- **Recall**: `0%`
- **F1-Score**: `0%`
- **AUC**: `49.87%`

---
### Final Evaluation

![evaluation](https://github.com/user-attachments/assets/7bf9b112-3fed-46d3-a07c-f64e63c01712)

#### 1. **Accuracy:**
   - **CNN** achieved the highest accuracy at 0.8922, followed by **VGG** at 0.8617, and **ResNet** with the lowest accuracy at 0.8571.

#### 2. **Loss:**
   - **CNN** has the lowest loss value at 1.1786, followed by **VGG** at 1.6514, and **ResNet** with the highest loss value at 1.9471.

#### 3. **Precision:**
   - **VGG** outperforms other models in precision at 0.7683, followed by **CNN** at 0.7475. **ResNet** has no precision score (0.0000).

#### 4. **Recall:**
   - **CNN** has the highest recall value at 0.3705, followed by **VGG** at 0.0461, and **ResNet** with no recall score (0.0000).

#### 5. **AUC (Area Under Curve):**
   - **CNN** also leads in AUC with 0.8810, followed by **VGG** at 0.7417, and **ResNet** with the lowest AUC at 0.5000.

#### 6. **F1 Score:**
   - **CNN** scores the highest F1 score at 0.4610, followed by **VGG** at 0.0857, and **ResNet** with no F1 score (0.0000).

---

### **Overall Conclusion:**
- **CNN** consistently outperforms both **VGG** and **ResNet** across all metrics, with the highest accuracy, recall, AUC, and F1 score, along with the lowest loss.
- **VGG** performs well in precision but struggles with recall, AUC, and F1 score, and shows higher loss compared to CNN.
- **ResNet** doesn't perform well in most metrics, particularly in precision, recall, F1 score, and AUC.

**Final Model Ranking:**
1. **CNN** (Best performer overall)
2. **VGG**
3. **ResNet** (Least effective model)


