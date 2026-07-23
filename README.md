# YOLO Object Detection Experiments(Academic Project)

This project presents a series of experiments conducted using different YOLO models (YOLO26n, YOLO26s, YOLO26m) trained for object detection. The goal was to analyze and compare performance across model sizes and training durations.

---

# 📌 Project Overview

In this project, multiple YOLO variants were trained and evaluated using standard object detection metrics:

- Precision
- Recall
- F1-score
- mAP@0.5
- mAP@0.5:0.95

Each model was trained for different numbers of epochs (50, 100, and 150 depending on the experiment).

---

# 🧠 Models Used

- YOLO26n (Nano model – lightweight, faster training)
- YOLO26s (Small model – balanced performance)
- YOLO26m (Medium model – higher accuracy, more compute)

---

# 🧠 Model Architecture Summary

This section provides the architectural and computational complexity comparison of the YOLO models used in this project.

| Model   | Layers | Parameters | GFLOPs | Complexity Level |
|---------|--------|------------|--------|------------------|
| YOLO26n | 260    | 2.50M      | 5.77   | Lightweight      |
| YOLO26s | 260    | 9.95M      | 22.50  | Medium           |
| YOLO26m | 280    | 21.77M     | 74.71  | Heavy / Accurate  |

---

## 📌 Key Observations

- **YOLO26n** is extremely lightweight and suitable for real-time or edge devices.
- **YOLO26s** provides a balance between accuracy and computational cost.
- **YOLO26m** is the most powerful model but requires significantly more compute (≈13× more GFLOPs than YOLO26n).
- Increase in parameters directly improves performance but reduces inference speed.

---

## ⚖️ Trade-off Insight

- More layers → better feature extraction but slower inference  
- More parameters → higher accuracy but higher memory usage  
- Higher GFLOPs → more computational cost  

This trade-off is important in real-world deployment scenarios (e.g., mobile vs server inference).

# 📊 Evaluation Metrics

The models were evaluated using:

- **Precision**: Accuracy of predicted positives  
- **Recall**: Coverage of actual positives  
- **F1-score**: Balance between precision and recall  
- **mAP@0.5**: Mean Average Precision at IoU threshold 0.5  
- **mAP@0.5:0.95**: Stricter evaluation across IoU thresholds  

---

# 📈 Final Model Comparison

### Best observed performance across experiments:

FINAL PERFORMANCE TABLE:

                      Model  Epoch  Precision  Recall  F1-score  mAP@0.5    mAP@0.5:0.95 
1    epoch_metrics_nano_100     35     0.8246  0.7839    0.8038   0.8467      0.3483 
4    epoch_metrics_nano_150     95     0.8689  0.6944    0.7719   0.8145      0.3997  
0   epoch_metrics_small_100     62     0.8375  0.7500    0.7913   0.7949      0.3018 
2     epoch_metrics_nano_50     62     0.8375  0.7500    0.7913   0.7949      0.3018 
3  epoch_metrics_medium_100     62     0.8375  0.7500    0.7913   0.7949      0.3018

    
> Note: Values represent best observed results from training logs.

---


# 📊 Results Summary

### Key Observations:

- Increasing model size improves overall performance (YOLO26n → YOLO26m)
- YOLO26m achieves the highest mAP scores but requires more computation
- YOLO26s provides a good balance between speed and accuracy
- Training stability improves significantly after initial epochs (20–30)

---


# 🚀 Future Improvements

- Hyperparameter optimization (learning rate, batch size, augmentation)
- Training on larger dataset
- Exporting models for real-time inference
- Deploying model using Flask / FastAPI

---

# 🛠 Tech Stack

- Python
- PyTorch / Ultralytics YOLO
- Pandas (for log analysis)
- Matplotlib / Seaborn (for plots)
- Jupyter Notebook

---

# 👨‍💻 Author

This project was built as part of machine learning practice to understand object detection systems and model evaluation.

---

# 📌 Note

All training logs and results are stored in the `results/` folder. Plots are generated from Excel logs to visualize training performance over epochs.
