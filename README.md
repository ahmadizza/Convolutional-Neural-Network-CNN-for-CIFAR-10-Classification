# Convolutional Neural Network (CNN) for CIFAR-10 Classification

*UTS Deep Learning Project*

## Project Description

This project aims to build and evaluate **Convolutional Neural Network (CNN)** models for classifying images in the **CIFAR-10** dataset. In addition, the project compares the performance of a **Custom CNN** architecture with **ResNet-18**, and applies **hyperparameter tuning** to improve accuracy.

Main objectives of the project:

* Classify **10 CIFAR-10 object categories**.
* Compare the performance of **Custom CNN vs ResNet-18**.
* Perform **hyperparameter tuning** (learning rate, batch size, optimizer, scheduler).
* Analyze **feature maps** and **confusion matrix** to understand the model behavior.

---

## Dataset: CIFAR-10

CIFAR-10 contains **60,000 color images (32×32)** categorized into 10 classes:

`plane, car, bird, cat, deer, dog, frog, horse, ship, truck`

Data splits:

* **45,000** images → training
* **5,000** images → validation
* **10,000** images → testing
* `set_seed(42)` is used for reproducibility.

---

## Model Architectures

### Custom CNN

* Network depth: **shallow** (8 convolutional layers)
* Optimizer: **Adam**
* Learning Rate: **0.001**
* Batch Size: **32**
* Scheduler: **ReduceLROnPlateau**

### ResNet (ResNet-18)

* Network depth: **deep** (18 layers + residual blocks)
* Optimizer: **SGD**
* Learning Rate: **0.1**
* Batch Size: **128**
* Scheduler: **CosineAnnealingLR**

### Performance Comparison

| Aspect                 | CNN                     | ResNet                                       |
| ---------------------- | ----------------------- | -------------------------------------------- |
| Test Accuracy          | **87%**                 | **94.64%**                                   |
| Network Depth          | Shallow (8 conv layers) | Deep (18 layers + residual blocks)           |
| Generalization Ability | Good                    | Very strong                                  |
| Overfitting            | Not observed            | Minimal                                      |
| Feature Map Analysis   | Captures basic features | Captures complex and highly focused features |
| Architecture           | Lightweight custom CNN  | ResNet with skip-connections                 |

---

## Results and Analysis

### Model Performance

* **CNN** achieved a test accuracy of **87%**.
* **ResNet-18** achieved a validation accuracy of **94.64%**.
* Loss and accuracy curves were stable for both models.
* Small gaps between training and validation metrics indicate **no overfitting**.

### Hyperparameter Tuning Effects

Performance improved significantly after tuning:

* Learning rate
* Batch size
* Optimizer
* Learning rate scheduler

ResNet benefited greatly from the combination of **SGD + CosineAnnealingLR**.

### Feature Map Analysis

* Both models develop hierarchical feature representations.
* ResNet produces **sharper and more complex** features compared to the custom CNN.
* The confusion matrix highlights classes that are most frequently misclassified.

---

## Evaluation

Evaluation was conducted using:

* Accuracy (train/validation/test)
* Loss curves
* Confusion matrix
* Feature map visualization
* Architectural and generalization comparison

---

## Conclusion

* Both the Custom CNN and ResNet perform well on CIFAR-10 classification.
* **ResNet consistently outperforms the Custom CNN** in accuracy, depth-based learning, and generalization.
* Hyperparameter tuning plays a significant role in improving model performance.
* Feature map analysis shows that **ResNet is more effective in extracting complex features**, contributing to its higher accuracy.

---

## Optional: Repository Structure

```
.
├── models/
├── notebooks/
├── images/
├── README.md
└── requirements.txt
```

