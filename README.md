
---

# YOLOv1 Implementation in PyTorch

This repository provides a YOLOv1 object detection model implemented in PyTorch. The model is organized into modular components:

- **BackboneModel**: Extracts features from the input image.
- **ConnectionLayer**: Connects features from the backbone to the YOLO head.
- **YOLOHead**: Predicts bounding boxes, class probabilities, and confidence scores.
- **Mapper**: Interface for converting tensors to labels and vice versa.
- **TensorToLabel / LabelToTensor**: Implements tensor-label conversions.
- **LossFunction**: Computes the loss value based on predictions and ground truth.
- **NonMaxSuppression**: Removes overlapping bounding boxes during inference.
- **YOLOInfo**: Contains configuration details such as number of classes, anchor boxes, and grid size.
- **TrainingLoop**: Manages the training process, including loss calculation and optimization.

### Workflow

1. **Input Image** -> **BackboneModel**: Extracts features.
2. **BackboneModel** -> **ConnectionLayer**: Processes features.
3. **ConnectionLayer** -> **YOLOHead**: Produces predictions.
4. **YOLOHead** -> **Mapper**: Converts raw predictions.
5. **Mapper** -> **NonMaxSuppression**: Filters boxes during inference.
6. **TrainingLoop** -> **Mapper**: Handles ground truth and encoded labels.
7. **Mapper** -> **LossFunction**: Calculates loss.
8. **LossFunction** -> **TrainingLoop**: Updates model parameters.

For detailed instructions, refer to the notebook provided.

---